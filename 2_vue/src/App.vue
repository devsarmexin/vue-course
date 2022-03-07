<template>
    <div class="app">
        <form>
            <H4>Создание поста</H4>
            <input v-bind:value="title" class="input" type="text" placeholder="название">
            <input v-bind:value="body" class="input" type="text" placeholder="описание">
            <button class="btn" @click="createPost">Создать</button>
        </form>
        <div>
            <div class="post" v-for="post in posts">
                <div><strong>Название:</strong> {{ post.title }}</div>
                <div><strong>Название:</strong> {{ post.body }}</div>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        data() {
            return {
                posts: [
                    {id: 1, title: 'JavaScript1', body: 'Орисание поста1'},
                    {id: 2, title: 'JavaScript2', body: 'Орисание поста2'},
                    {id: 3, title: 'JavaScript3', body: 'Орисание поста3'}
                ],
                title: '',
                body: ''
            }
        },
        methods: {
            createPost() {

            }
        }
    }
</script>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    .app {
        padding: 20px;
    }

    .post {
        padding: 15px;
        border: 10px solid teal;
        margin-top: 15px;
    }

    form {
        display: flex;
        flex-direction: column;
    }

    .input {
        width: 100%;
        border: 1px solid teal;
        padding: 10px 15px;
        margin-top: 15px;
    }

    .btn {
        margin-top: 15px;
        align-self: flex-end;
        padding: 10px 15px;
        background: none;
        color: teal;
        border: 1px solid teal;
    }
</style>