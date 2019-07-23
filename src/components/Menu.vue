<template>
        <el-menu
      default-active="1-1"
      class="el-menu-vertical-demo"
      @open="handleOpen"
      @close="handleClose">
      <menu-item v-for="route in menuList" :key="route.path" :item="route" :base-path="route.path" />
    </el-menu>
</template>
<script>
import MenuItem from './Menuitem'
export default {
    data(){
        return{
            menuList:[
                {
                    path:'/index',
                    title:'首页',
                    icon:'home',
                },
                {
                    path:'/article',
                    title:'文章管理',
                    icon:'home',
                    children:[
                        {
                            path:"/article/list",
                            title:'文章列表',
                            hidden:true
                        },
                        {
                            path:"/article/add",
                            title:'新增文章',
                            hidden:true
                        }
                    ]
                },{
                    path:'about',
                    title:'关于我们',
                }
            ]
        }
    },
    components:{
        MenuItem
    },
     methods: {
      handleOpen(key, keyPath) {
        console.log(key, keyPath);
      },
      handleClose(key, keyPath) {
        console.log(key, keyPath);
      }
    }
}
</script>
<style lang="stylus">
.default-scrollbar {
      overflow-x:hidden;
}
</style>


