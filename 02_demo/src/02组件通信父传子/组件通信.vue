<template >
  <div>
<!--  父组件传递给子组件-->
  <ul >
    <li >姓名：{{name}}</li >
    <li >年龄：{{age}}</li >
    <li >性别：{{sex}}</li >
  </ul >

<!--  子传父-->
    <div>
      <p>当子组件发生变化时 如点击事件 父组件需要切换内容 </p>
      <p> 或者子组件要传递内容給父组件</p>
      <p> 实现方式：父组件使用 v-on 方式传入要监听的事件名，绑定到方发中 </p>
      <p>子组件触发事件后根据  根据事件名触发对应事件</p>
    </div>





  </div>

</template >

<script >
export default {
  name: "tongxin",
  //使用props关键字以数组的形式接受  父组件传入的属性
  props: ["name", "age", "sex"],//数值语法--弊端不能验证对象类型
  //对象语法---》可以检测数据类型
  // props:{
  //    name：{               ------------》属性名可以是对象的形式里面包含属性和默认值
  //        type:string,
  //        required:true,---->默认是false  设置为true表示必须传值
  //        default:"默认值"
  //    }，
  //    age：number，
  //    sex：string
  //------注意：如果传入的是对象类型要想有默认值  那么要以函数形式进行处理
  //    friend:{
  //    type:object,
  //    default:()=>（{name:""杰西卡}）
  //    }
  // ----数组有默认值的话--也要写一个函数
  //    hibbies:{
  //    type:Array,
  //    default:()=>(["唱","跳"])
  //    }
  //-----还有注意命名规则 如果以驼峰形式写：showMessage   那父级要么同名要么 show-message
  // }
  inheritAttrs:false,
};
</script >

<style scoped >

</style >