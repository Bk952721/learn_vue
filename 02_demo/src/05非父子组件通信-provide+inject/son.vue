<template >
<div class="son">
  我是子级标签,背景是红色的
  <grandson></grandson>
  666666
</div>
</template >

<script >
import grandson from "./grandson";
export default {
  components:{grandson},
  name: "son"
}
</script >

<style scoped >
.son{
  background-color: red;
}
</style >