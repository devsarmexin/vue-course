<template>
    <div>
        <button v-on:click="addLike">Like</button>
        <button v-on:click="addDisLike">Dislike</button>
    </div>
    <div>
        <div>Количество лайков <strong>{{ likes }}</strong></div>
        <div>Количество дизлайков <strong>{{ dislikes }}</strong></div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            likes: 0,
            dislikes: 0,
        }
    },
    methods: {
        addLike() {
            this.likes += 1;
        },
        addDisLike() {
            this.dislikes += 1;
        }
    }
}
</script>

<style>

</style>