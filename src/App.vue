<script>
import Model from './Components/model.vue';
export default {
    data() {
        return {
            showModelComponent: false,
            theme: 'sale',
            applyTheme:true
        }
    },
    methods: {
        onFocus() {
            this.$refs.inputRef.focus();
        },
        showModel() {
            this.showModelComponent = !this.showModelComponent;
        },
        changeTheme(){
            this.theme=this.theme==='sale'?this.theme='normal':this.theme='sale';
            this.applyTheme=!this.applyTheme
        }
    },
    components: {
        Model
    }
}
</script>
<template>
    <div class="main-container">
      <h1>Model Project</h1>
      <input type="text" ref="inputRef" />
      <button @click="onFocus">FOCUS</button>
      <button @click="showModel">Open Model</button>
      <Model v-if="showModelComponent" :showModel="showModel" :title="`Sign up for the Giveaway!`"
          :content="`Grab your ninga swag for half price!`" :theme="theme"
          :applyTheme="applyTheme">
        <template v-slot:links >
          <div class="slot-container">
            <p :class="{'theme-text-color':applyTheme, 'content': !applyTheme}">Do It Fast!!!</p>
            <div class="buttons">
              <button :class="{'theme-btn-color': applyTheme, 'btn-color': !applyTheme}" >Sign Up</button>
              <button :class="{'theme-btn-color': applyTheme, 'btn-color': !applyTheme}">Login</button>
              <button :class="{'theme-btn-color': applyTheme, 'btn-color': !applyTheme}" @click="changeTheme" >Change Theme</button>
            </div>
          </div>
        </template>
      </Model>
    </div>
  </template>

<style scoped>
body {
    margin: 0;
   box-sizing: border-box;
}

.main-container {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-family: sans-serif;
}

input {
    height: 26px;
    width: 11rem;
    border-radius: 7px;
    margin-bottom:20px;
    border:none;
    border:2px solid rgb(169, 167, 167)
}

 button {
    padding: 5px 10px;
    background-color: white;
    margin-bottom: 10px;
    border:none;
    border:2px solid rgb(169, 167, 167);
    border-radius: 5px;
    cursor:pointer;
}

 button:hover {
    background-color: black;
    color: white;
}
.slot-container .buttons {
    display: flex;
    gap: 20px;
}

.slot-container .btn-color {
    color: rgb(10, 212, 182);
    border-color: rgb(10, 212, 182);
    background-color: white;
    cursor: pointer;
}

.slot-container .btn-color:hover {
    background-color: rgb(10, 212, 182);
    color: white;
}
.slot-container .theme-btn-color {
    color:white;
    border-color:white;
    background-color: red;
    cursor: pointer;
}

.slot-container .theme-btn-color:hover {
    background-color:white;
    color: red;
}
.slot-container .theme-text-color{
    color:white
}
.slot-container .content{
    color:black;
}
</style>
