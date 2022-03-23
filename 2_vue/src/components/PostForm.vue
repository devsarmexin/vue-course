<template>
    <form @submit.prevent>
        <H4>Создание поста</H4>
        <my-input
                v-model="post.title"
                type="text"
                placeholder="название"></my-input>
        <my-input v-model="post.body"
                  type="text"
                  placeholder="описание"></my-input>
        <my-button
                style="align-self: flex-end; margin-top: 15px"
                @click="createPost"
        >
            Создать
        </my-button>
    </form>
</template>

<script>
    export default {
        data() {
            return {
                post: {
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            createPost() {
                this.post.id = Date.now();
                this.$emit('create', this.post)
                this.post = {
                    title: '',
                    body: ''
                }
            }
        }
    }

</script>

<style scoped>
    form {
        display: flex;
        flex-direction: column;
    }

</style>

