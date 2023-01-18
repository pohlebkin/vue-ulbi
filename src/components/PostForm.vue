<template>
    <form @submit.prevent>
        <h4>создание поста</h4>
        <my-input
            v-model="post.title"
            placeholder="название"
        />
        <my-input
            v-model="post.body"
            placeholder="описание"
        />
        <my-button
            style="align-self: flex-end;"
            @click="createPost"
        >
            создать
        </my-button>
    </form>
</template>


<script>
export default{
    data(){
        return {
            post: {
                title: '',
                body: ''
            }
        }
    },
    methods: {
        createPost(){
            this.post.id = Date.now();
            this.$emit('create', this.post);
            this.post = {
                title: '',
                body: ''
            }
        }
    }
}
</script>


<style scoped>
form{
    display: flex;
    flex-direction: column;
}
</style>
