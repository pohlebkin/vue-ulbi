<template>
    <div>
        <button @click="addLike">like</button>
        <button @click="addDislike">dislike</button>
    </div>
    <div>кличество лайков: <b>{{ likes }}</b></div>
    <div>кличество дизлайков: <b>{{ dislikes }}</b></div>
</template>

<script>
export default{
    data(){
        return{
            likes: 0,
            dislikes: 5,
        }
    },
    methods: {
        addLike(){
            this.likes += 1;
        },
        addDislike(){
            this.dislikes += 1;
        },
    },
}
</script>

<style>

</style>

