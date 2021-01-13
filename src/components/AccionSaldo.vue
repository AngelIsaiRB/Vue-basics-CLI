<template>
  <button @click="accion" :disabled="disabled">{{texto}}</button>
</template>

<script>
export default {
    props:{
        texto:String,
        disabled: {
            type:Boolean,
            default:false
        }
    },
    methods:{
        accion(){
            this.$emit("accion")
        }
    }
}
</script>

<style scoped>
button {
display: inline-block;
padding: 15px 25px 10px 10px;
margin: 10px 10px 10px 10px;
font-size: 24px;
cursor: pointer;
text-align: center;
text-decoration: none;
outline: none;
color: white;
background-color: CORAL;
border: none;
border-radius: 15px;
box-shadow: 0 10px #999;
}
button:hover {background-color: coral}
button:active {
background-color: coral;
box-shadow: 0 5px #666;
transform: translateY(4px);
}
</style>