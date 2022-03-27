<template>
    <div class="navBar">
        <div @click="$router.push('/')">Обучающее приложение по Vue</div>
        <div class="navBar__btns">
            <my-button @click="$router.push('/posts')">Посты</my-button>
            <my-button style="margin-left: 20px" @click="$router.push('/about')">О сайте</my-button>
        </div>
    </div>
</template>

<script>
    export default {

    }
</script>

<style scoped>
    .navBar {
        height: 50px;
        background: lightgray;
        box-shadow: 2px 2px 4px gray;
        display: flex;
        align-items: center;
        padding: 0 15px;
    }
    .navBar__btns {
        margin-left: auto;
    }
</style>