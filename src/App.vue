<template>
    <div class="app">
        <h1>страница с постами</h1>
        
        <my-button
            @click="showDialog"
        >
            создать пост
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
// @ в пути означает папку src
import PostForm from '@/components/PostForm.vue';
import PostList from '@/components/PostList.vue';
import axios from 'axios';

export default{
    components: {
        PostList, PostForm
    },
    data(){
        return{
            posts: [],
            dialogVisible: false,
            modificatorValue: '',
        }
    },
    methods: {
        createPost(post){
            this.posts.push(post);
            this.dialogVisible = false;
        },
        removePost(post){
            this.posts = this.posts.filter(p => p.id !== post.id)
        },
        showDialog(){
            this.dialogVisible = true;
        },
        async fetchPosts(){
            try{
                const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
                this.posts = response.data;
                console.log(response);
            }catch(e){
                alert('ошибка');
            }
        }
    },
    mounted(){
        this.fetchPosts();
    }
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

