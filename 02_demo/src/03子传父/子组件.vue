<template >
<div>
  <button @click="adds(1)">+1</button>
  <button @click="adds(5)">+5</button>
  <button @click="adds(10)">+10</button>
</div>
</template >

<script >
export default {
  emits:['addss'],
  name: "ccc",
  methods:{
    adds(cont){
      // this.$emit("adds",cont)
     this.$emit("addss",cont)
    }
  }
}
</script >

<style scoped >

</style >