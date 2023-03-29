<template >
  <div class="grandson">
    我是孙级标签----背景是绿色的
    这是通过provide+inject 获取来自app组件的数据
   showtime--> 展示 {{meg.value}}
  </div>

</template >

<script >
export default {
  name: "grandson",
  inject:["meg"]
}
</script >

<style scoped >
.grandson{
  background-color: green;
}

</style >