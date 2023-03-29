<template >
<div>
  <p>非父子父组件之间通信【不依赖第三方管理库】</p>
  <p>1.provide+inject    2.事件总线</p>
  <div>
    非父子组件通信产生原因：有一些嵌套比较深的组件想要得到父组件的部分内容<br>
    如：孙级组件想要获取父级组件信息   父 -》子-》孙  使用props会很麻烦
  </div>
  <div>
    1.provide+inject                               <br>
    父组件组成provide事件----子组件使用inject接收     <br>
    可看作给子孙组件添加了一个长属性【long range props】  父，子孙都不知道数据来源，用途<br>
    局限性--只用在有同一个祖先组件时适用  且数据有共同祖先提供
  </div>
  <son></son>
</div>
</template >

<script >
import son from './son'
import {computed} from "vue";
export default {
  name: "app",
  components:{son},
  data(){
    return{
      meg:'父级传递给孙级'
    }
  },
  //发出数据---目前是写死的---使用函数写法【这里不能直接使用this】
  // provide:{
  //   name:'魂牵',
  // },



  //函数写法----这样是直接赋值 【不能实现动态化--就是父级属性改变来孙级的数据不会变】
  // provide(){
  //   return {
  //     meg:this.meg
  //   }
  // }

  //实现动态的话需要借助 computer函数  1.先从vue引入  使用是要return 返回值
  //但是会出现双引号 -应为没有解包 --解决方法 孙级组件使用属性是在后面添加.value
  provide(){
    return {
      meg:computed(()=>{return this.meg})
    }
  }

}
</script >

<style scoped >

</style >