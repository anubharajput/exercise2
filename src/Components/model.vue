<template>
    <div class="empty-container" @click="customFunction()"></div>
    <div class="box" :class="{'text-bg':theme==='sale'}">
        <h1 :class="{'text-color': theme === 'sale', 'title': theme !== 'sale'}">
            {{ title }}
        </h1>
        <p :class="{'text-color': theme === 'sale'}">{{ content }}</p>
        <div class="modal-content">
      <slot name="links"></slot>
    </div>
    </div>
</template>
<script>
export default {
    props: ['customFunction','title','content','theme'],
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

.box .title {
    color: rgb(10, 212, 182);
}


.empty-container {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .7);
    cursor: pointer;
}
.text-color{
    color:white;
}
.text-bg{
    background-color: red;
}

</style>