<template>
  <div class="home">
    <h1>{{msg.a}}</h1>
    <img alt="Vue logo" src="@/assets/logo.png">
    <HelloWorld :msg="msg" @toparent="getIt"/>
  </div>
</template>

<script>
// @ is an alias(别名) to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Vue from 'vue'
export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data(){
    return {
      msg:{
        a:'1'
      }
    }
  },
  mounted(){

  },
  methods:{
    getIt(value){
      // this.msg=value
      console.log('传过来了')
      Vue.set(this.msg,'a',value)
    }
  }
}
</script>
