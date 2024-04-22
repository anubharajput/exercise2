<template>
    <div class="backdrop-container" @click="showModel()"></div>
    <div class="box" :class="{'theme-background':theme==='sale'}">
        <h1 :class="{'theme-text-color': applyTheme, 'text-color': !applyTheme}">
            {{ title }}
        </h1>
        <p :class="{'theme-text-color': applyTheme}">{{ content }}</p>
        <div class="modal-content">
      <slot name="links"></slot>
    </div>
    </div>
</template>
<script>
export default {
    props: ['showModel','title','content','theme','applyTheme'],
}
</script>
<style scoped>
.box {
    position: absolute;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    background-color: white;
    padding: 20px;
    width: 30%;
    margin: auto;
    margin-top: 100px;
    border-radius: 10px;
    z-index: 1;
}

.box .text-color {
    color: rgb(10, 212, 182);
}


.backdrop-container {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .7);
    cursor: pointer;
}
.theme-text-color{
    color:white;
}
.theme-background{
    background-color: red;
}

</style>