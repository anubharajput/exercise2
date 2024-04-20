<template>
    <div class="empty-container" @click="customFunction()"></div>
    <div class="box">
        <h1>Sign up for the Giveaway!</h1>
        <p>Grab your ninga swag for half price!</p>
        <p>Do It Fast!!!</p>
        <div class="buttons">
            <button>Sign Up
            </button>
            <button>Login</button>
        </div>
    </div>
</template>
<script>
export default {
    props: ['customFunction'],
}
</script>
<style scoped>
.box {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: beige;
    padding: 20px;
    width: 30%;
    margin: auto;
    margin-top: 50px;
    border-radius: 10px;
    z-index: 1;
}

.box h1 {
    color: rgb(10, 212, 182);
}

.box .buttons {
    display: flex;
    gap: 20px;
}

button {
    color: rgb(10, 212, 182);
    border-color: rgb(10, 212, 182);
    background-color: white;
}

button:hover {
    background-color: rgb(10, 212, 182);
    color: white;
}

.empty-container {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .7);
    cursor: pointer;
}
</style>