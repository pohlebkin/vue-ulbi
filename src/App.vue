<template>
    <div>
        <div class="post" v-for="post in posts">
            <div><strong>Название:</strong> {{ post.title }}</div>
            <div><strong>Описание:</strong> {{ post.body }}</div>
        </div>
    </div>
</template>

<script>
export default{
    data(){
        return{
            posts: [
                {id: 1, title: 'джаваскрипт 1', body: 'описание поста 1', },
                {id: 2, title: 'джаваскрипт 2', body: 'описание поста 2', },
                {id: 3, title: 'джаваскрипт 3', body: 'описание поста 3', },
                {id: 4, title: 'джаваскрипт 4', body: 'описание поста 4', },
            ]
        }
    },
    methods: {
    },
}
</script>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.post{
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}
</style>
