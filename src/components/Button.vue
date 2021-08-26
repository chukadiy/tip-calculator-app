<template>

<button class=btn @click="onClick()"> {{text}} </button>
    
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String,
    },

    methods: {
        onClick(){
          this.$emit("btn-click")

        }
    }
}
</script>

<style scoped> 

.btn {
  display: inline-block;
  background: hsl(183, 100%, 15%);
  color: #fff;
  border: none;
  width: 94px;
  height: 40px;
  padding: 10px Auto;
  margin: 6px;
  border-radius: 4px;
  cursor: pointer;
  text-decoration: none;
  font-size: 18px;
  font-weight: 700;
  font-family: inherit;
  z-index: 10;
  outline: none;
}

.btn:focus {
  background: hsl(172, 67%, 45%);
}



</style>