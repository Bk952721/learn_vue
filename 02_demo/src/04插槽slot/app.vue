<template>
  <div>
    <p>插槽的使用</p>
    <div>
      插槽：为了让组件具备更好的通用性【不能将组件内容限定为div或span】<br >
          如有些时候 希望组件显示按钮 有时又希望显示一张图片<br >
          让试用着决定某一区域存放什么内容和元素<br >
          使用案例---》几个导航栏结果都左中右  但显示不同---》抽出相同结果---》试用插槽展示不同内容<br>
    </div>
    <h3>
      插槽使用：抽取共同，预留不同，将共同元素和内容依然在组件中封装
      将不同元素使用slot作为站位符，外部决定展示
    </h3>
    <p>
      vue中：使用slot元素作为正常发布内容出口，组件封装中使用特殊元素slot 开启一个插槽
      插入内容由父级元素决定
    </p>
  </div>
  <div class="a1">

    <!--  展示一句话-->
    使用插槽
    <Son1>
      <p  class="a2">使用插槽中</p>
    </Son1>
    <hr >
    <!--    展示一个按钮-->
    <Son1>
      <button>这是一个按钮</button>
    </Son1>

  </div>
  <div>
    <p> 如果没有值 插槽就会别自动忽略   也可以在  slot标签里写值  ---这样插槽就会拥有默认值</p>
    <p> 如果一个组件有多个插槽</p>
  </div>

  <div>
    <p>具名插槽：多个插槽  </p>
    <p>方法：给子组件里的插槽添加name属性  </p>
    <pre>
      演示：子组件
      《div》
      《slot name='left'》默认值1《/slot》
      《/div》

      《div》
        《slot name='conter'》默认值1《/slot》
      《/div》

      《div》
        《slot name='right'》默认值1《/slot》
      《/div》

      父组件使用：需要使用模板  template  slot:插槽名
      《div》
          《template v-slot:left》内容《/template》
          《template v-lot:conter》内容《/template》
          《template v-slot:right》内容《/template》
      《/div》
    </pre>
    <p>如果一个插槽不自定义名，系统会自动给他添加一个隐藏名字default</p>
    <p>还可以动态插槽名：【就是插槽名从data里面获取 注意书写方式是】 template slot:[动态插槽名] </p>
  </div>

  <div>
    注意：插槽名不能不是等于号   有语法糖‘#’
  </div>
  <div>
    渲染作用域：父模块里面的内容都是在父级作用域编译的 即便引入子级的组件 里面有插槽<br>
    他还是在父级里面渲染的，读取数据读取的也是父级的数据
    <hr >
    子级实在子级组件的作用域里渲染的，数据也都是在子级里面读取的
    <hr >
    <h2>小结：不管有没有子级，子级有没有插槽，数据的读取都是从本身作用域开始的【传值情况除外】</h2>
  </div>


  <div>
    作用域插槽：例子： 由父级决定插槽里面的数据是什么类型的【超链接----按钮啥的】<br >
    但是数据是插槽里面数据是子组件处理出来的---由于插槽作用域的原因：父级无法直接使用子级的数据展示<br>
    <p>解决方案  子级传递</p>
    <pre>
      案例
      子级
      《slot :item》-----将item传递到父级
          《span》来着子级的数据使用双花括号语法{{}}《/span》------父级可以改变span  改成按钮，超链接啥的
      《/slot》

      父级
      《template #default="自定义名称"》------》default 设置插槽时默认添加的名字可以通过他找的插槽【跟具名插槽一样的】
            《button》    ------------>改变插槽里的span
                自定义名称.item-------->使用花括号语法包裹【default里面包含了插槽里的所有数据】
            《/button》
      《/template》


      独占默认插槽的写法
      v-slot="自定义插槽名"《===》 v-slot:default="自定义插槽名"《===》 #default="自定义名称"
    </pre>
    <h2>当只有一个插槽时 template 标签是可以省略的   但是用到多个插槽的话就不能省略  </h2>
  </div>


</template>
<script>
import Son1 from "@/04插槽slot/son1";
export default ({
components:{Son1}
})

</script>

<style>
.a1{
  background-color: orange;
}
.a2{
  background-color: red;
}

</style>