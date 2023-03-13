<template>
  <div>
    <p>文件补充说明</p>
    <ul>
      <li>jspmfig.json --->主要租用：方便编辑器对编写时提供更好的提示</li>
      <li>引入的vue和默认导入的vue 版本不同 ：
        引入的：在vue根目录  <br>
        使用const app创建的一个对象在   import{createApp} from 'vue' 是不支持template的<br>
        要支持就要引入  import{} form 'vue /dist/nba/index' 才行
        <pre>
          import{createApp} from 'vue' 不支持这样
          const app={
          template："******"
          }
          改成import{} form 'vue /dist/nba/index' 才行
        </pre>
      </li>
      <li>设置自己文件的作用域：在style后面添加scoped[只会在自己的本文件生效不会影响到其他组件]</li>
    <li>创建vue项目的第二种方式  使用vite   命令：npm init vue@latest <br>
    过程：先安装一个本地工具  create-vue  使用create-vue创建一个vue项目
    </li>
    </ul>
  </div>

</template>
<script>
export default ({
  name:"01buchong"
})
</script>

<style scoped>

</style>