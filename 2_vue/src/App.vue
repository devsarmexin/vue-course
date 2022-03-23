<template>
    <div class="app">
        <h1>Страница с постами</h1>
        <input type="text" v-model.trim="modificatorValue">
        <my-button @click="fetchPost">Получить посты</my-button>
        <my-button
               @click="showDialog"
               style="margin: 15px 0;"
        >
            Создать пост
        </my-button>
        <my-dialog v-model:show="dialogVisible">
            <post-form
                    @create="createPost"
            />
        </my-dialog>
        <post-list
                :posts="posts"
                @remove="removePost"
        />
    </div>

</template>

<script>
    import PostForm from "@/components/PostForm";
    import PostList from "@/components/PostList"
    import MyDialog from "@/components/UI/MyDialog";
    import axios from "axios"
    import MyButton from "@/components/UI/MyButton";

    export default {
        components: {
            MyButton,
            MyDialog,
            PostForm, PostList
        },
        data() {
            return {
                posts: [
                    {id: 1, title: 'JavaScript1', body: 'Орисание поста1'},
                    {id: 2, title: 'JavaScript2', body: 'Орисание поста2'},
                    {id: 3, title: 'JavaScript3', body: 'Орисание поста3'},
                    {id: 4, title: 'JavaScript4', body: 'Орисание поста4'},
                    {id: 4, title: 'JavaScript5', body: 'Орисание поста5'}
                ],
                dialogVisible: false,
                modificatorValue: ''
            }
        },
        methods: {
            createPost(post) {
                this.posts.push(post);
                this.dialogVisible = false;
            },
            removePost(post) {
                this.posts = this.posts.filter(p => p.id !== post.id)
            },
            showDialog() {
                this.dialogVisible = true;
            },
            async fetchPost() {
                try {
                    const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
                    console.log(response)
                } catch (e) {
                   alert('ОШИБКА')
                }
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
</style>