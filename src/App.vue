<script>
import Model from './Components/model.vue';
export default {
    
   data(){
    return{
        message:null,
        hideShow:false,
        showComponent:false
            }
   },
   methods:{
      onFocus(){
        this.$refs.inputRef.focus();
      },
      customFunction(){
        this.showComponent=!this.showComponent;
      }
   },
   components: {
    Model
  }
}
</script>

<template>
     <body>
<div class="main-container">
    <h1>Model Project</h1>
<input type="text" v-model="message" placeholder="edit me" ref="inputRef"/>
<p>Message is: {{ message }}</p>
<button @click="onFocus">FOCUS</button>
<button @click="customFunction">Open Model</button>
<Model v-if="showComponent" :customFunction="customFunction"/>

</div>
</body>
</template>

<style scoped>
body{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
.main-container{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
input{
    height: 26px;
    width: 11rem;
    border-radius: 7px;
    border-color:rgb(242, 234, 234);
}
button{
    padding:5px 10px;
    background-color: white;
    margin-bottom: 10px;
}
button:hover{
    background-color: black;
    color:white;
}
</style>

