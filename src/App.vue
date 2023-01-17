<template>
    <div class="app">
        <post-form @create="createPost"/>
        <post-list :posts="posts"/>
    </div>
</template>


<script>
// @ в пути означает папку src
import PostForm from '@/components/PostForm.vue';
import PostList from '@/components/PostList.vue';

export default{
    components: {
        PostList, PostForm
    },
    data(){
        return{
            posts: [
                {id: 1, title: 'джаваскрипт 1', body: 'описание поста 1', },
                {id: 2, title: 'джаваскрипт 2', body: 'описание поста 2', },
                {id: 3, title: 'джаваскрипт 3', body: 'описание поста 3', },
                {id: 4, title: 'джаваскрипт 4', body: 'описание поста 4', },
            ],
        }
    },
    methods: {
        createPost(post){
            this.posts.push(post);
        },
    },
}
</script>


<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Verdana, sans-serif;
    font-size: 18px;
}

.app{
    padding: 20px;
}

</style>

