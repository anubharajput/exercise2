<script>
import Model from './Components/model.vue';
export default {

    data() {
        return {
            message: null,
            hideShow: false,
            showModelComponent: false,
            theme: 'sale'
        }
    },
    methods: {
        onFocus() {
            this.$refs.inputRef.focus();
        },
        showModel() {
            this.showModelComponent = !this.showModelComponent;
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
      <input type="text" placeholder="edit me" ref="inputRef" />
      <button @click="onFocus">FOCUS</button>
      <button @click="showModel">Open Model</button>
      <Model v-if="showModelComponent" :showModel="showModel" :title="`Sign up for the Giveaway!`"
          :content="`Grab your ninga swag for half price!`" :theme="theme">
        <template v-slot:links >
          <div class="container">
            <p :class="{'text-color': theme === 'sale', 'content': theme !== 'sale'}">Do It Fast!!!</p>
            <div class="buttons">
              <button :class="{'theme-btn-color': theme === 'sale', 'btn-color': theme !== 'sale'}">Sign Up</button>
              <button :class="{'theme-btn-color': theme === 'sale', 'btn-color': theme !== 'sale'}">Login</button>
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
}

 button:hover {
    background-color: black;
    color: white;
}
.container .buttons {
    display: flex;
    gap: 20px;
}

.container .btn-color {
    color: rgb(10, 212, 182);
    border-color: rgb(10, 212, 182);
    background-color: white;
}

.container .btn-color:hover {
    background-color: rgb(10, 212, 182);
    color: white;
}
.container .theme-btn-color {
    color:white;
    border-color:white;
    background-color: red;
}

.container .theme-btn-color:hover {
    background-color:white;
    color: red;
}
.container .text-color{
    color:white
}
.container .content{
    color:black;
}
</style>
