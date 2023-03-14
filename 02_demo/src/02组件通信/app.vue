<template >
  <div>
    <p>组件嵌套关系</p>
    <p>开发时如果只使用一个组件，将所有逻辑放在一起会很臃肿， 所以要对组件进行拆分，在讲组件嵌套在一起</p>
  </div>
  <h2>父传子：通过props属性</h2>
  props：给组件注册自定义的attribute----父组件给这些东西赋值----子组件通过他对应名称获取值
  <h2>子传父：通过$emit属性</h2>
  <hr >
  <p>案例</p>
  <p>父-->子</p>
  <tongxin name="张三" age="19" sex="男" />
  <tongxin name="李四" age="100" sex="女" />
  如果：当前的属性是一个非prop的attribute[就是添加属性 但是子组件没有接收的peops]
  <br >
  那么该属性会默认添加到子组件的根元素上【像是添加了id clsaa style一样的属性】
  <br >当组件有根节点【也就是子组件有一个根节点】非prop的attribute就会自动添加到根节点的attribute中
  <br >不希望这样的话：在子组件添加inheritAttrs:false,他就不会加进来了
  <br >如果禁用了还想要那   在相应添加的表情上添加 :class="$attrs.想要获取的属性名"---$attrs固定语法

</template >


<script >
import tongxin from './组件通信.vue'
export default {
  name: "app",

  components:{
    //子组件
    tongxin
  }
}
</script >

<style scoped >

</style >