<template >
<div>
  <p>{{count}}</p>
  <ccc v-on:addss="jiafa"></ccc>
  <div>
    <p>子传父  子组件有点击事件   通过 在事件中添加 this.$emit(自定义事件名 ,传递参数)     将数据传递给父组件</p>
    <p>父组件使用 v-on:事件名="自定义的处理时间"  简写 @自定义事件名=处理事件 </p>
    <pre>
      父
      <ccc v-on:addss="jiafa"></ccc>
      methods:{
        jiafa(cont){
        console.log(cont)
        this.count+=cont
      }
    }

      子
      <button @click="adds(1)">+1</button>
      <button @click="adds(5)">+5</button>
      methods:{
        adds(cont){
      第一个值：自定义事件名    第二个值 传递参数
          this.$emit("addss",cont)
        }
      }
    </pre>
  </div>
  开发式 子组件添加 一个 emits属性  将事展示出来 方便协作开发  写法：  在export default里面  emits['事件1','事件2','事件3'...]
  可以使用对象语法进行验证  emits：{自定义事件名：function(){if(){...}}    }
</div>
</template >

<script >
import ccc from "./子组件.vue"
export default {
  name: "app",
  components:{
    ccc
  },
  data(){
    return {
      count:0
    }
  },
  methods:{
    jiafa(cont){
      console.log(cont)
      this.count+=cont
    }
  }

}
</script >

<style scoped >

</style >