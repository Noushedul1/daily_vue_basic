<template>
  <div>
    <p>
      Lorem, ipsum dolor sit amet consectetur adipisicing elit. Eaque, dicta repudiandae. Cumque totam consequatur facilis quisquam aspernatur accusantium laboriosam voluptas, odit vitae temporibus adipisci eligendi rerum nulla maiores, cum ducimus!
    </p>
    <p>{{country}}</p>
    <p v-html="myhtml"></p>
    <p v-text="mymessage"></p>
    <p>
      {{myfavarite[0]}}
    </p>
    <div v-for="a in myfavarite" :key="a.id">
      {{a}}
    </div>
    <p>
      {{myobject.firstname}} {{myobject.lastname}}
    </p>
    <a :href="src">Google</a>
    <MyUniversity>
      <template v-slot:ak>
        <p>hello noushedul</p>
      </template>
      <template v-slot:ki>
        <p>hello software engineer</p>
      </template>
    </MyUniversity>
    <button @click="namechange()">Lastname Change</button>
    <p>{{age}}</p>
    <button @click="age=26">age change</button>
    <div v-if="age==25">
      yes the age is 25
    </div>
    <div v-else-if="age==26">
      yes the age is 26
    </div>
    <div v-else>
      yes the age is another 
    </div>
    <div v-show="country=='russia'">
      yes the country is russia 
    </div>
    <div v-show="country!=='russia'">
      yes the country name is Bangladesh
    </div>
    <div v-once>{{myobject.firstname}}</div>
    <div>{{myobject.firstname}}</div>
    <button @click="firstnamechange()">firstname change</button>
    <div class="box" v-on:mousemove="heightWidth">
      x {{x}}
      y {{y}}
    </div>
    <div class="details">
      hello noushedul islam akib. how are you what are you doing? 
    </div>
    <teleport to="#hello">
      <MyFooter></MyFooter>
    </teleport>
  </div>

</template>
<script>
import MyUniversity from './components/MyUniversity.vue';
import MyFooter from './components/MyUniversity.vue';
export default{
  name: 'App',
  components: {
    MyUniversity,
    MyFooter
  },
  data () {
    return {
    country: 'Bangladesh',
    myhtml: '<h1>hello noushedul islam akib</h1>',
    mymessage: 'i am a software engineer of southern university of bangladesh',
    myfavarite: [
      'shakib','tamim','mashrafee','moshfiq'
    ],
    myobject: {
      firstname: 'noushedul',
      lastname: 'islam'
    },
    src: 'https://google.com',
    age: 25,
    x: 0,
    y: 0
    }
  },
  methods: {
    namechange(){
      this.myobject.lastname = 'akib';
    },
    firstnamechange(){
      setTimeout(()=>{
        this.myobject.firstname = 'akib'
      },2000)
    },
    heightWidth(event){
      this.x = event.clientX;
      this.y = event.clientY;
    }
  }
}
</script>
<style scoped>
  .box{
    height: 200px;
    width: 150px;
    background: orange;
  }
  .details{
    background: green;
    color: white;
  }
</style>