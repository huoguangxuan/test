<template>
  <div class="hello">
    <h1>{{ cmsg }}</h1>
    <button @click="changeData">改变数据</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: Object
  },
  data(){
    return{
      cmsg:''
    }
  },
  computed:{
  },
  created(){
    this.cmsg=this.msg.a
  },
  methods:{
    changeData(){
      this.cmsg='123'
      //给父组件广播数据
      this.$emit('toparent',this.cmsg)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
h3
  margin 40px 0 0

ul
  list-style-type none
  padding 0

li
  display inline-block
  margin 0 10px

a
  color #42b983
</style>
