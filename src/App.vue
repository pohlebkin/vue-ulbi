<template>
    <div class="app">
        <form>
            <h4>создание поста</h4>
            <input
                v-bind:value="title"
                @input="title = $event.target.value"
                class="input"
                type="text"
                placeholder="название"
            >
            <input
                v-bind:value="body"
                @input="body = $event.target.value"
                class="input"
                type="text"
                placeholder="описание"
            >
            <button
                class="btn"
                @click="createPost"
            >создать</button>
        </form>
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
            ],
            'title': '',
            'body': '',
        }
    },
    methods: {
        createPost(){

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

.post{
    padding: 15px;
    border: 2px solid teal;
    margin-top: 15px;
}

form{
    display: flex;
    flex-direction: column;
}

.input{
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
}

.btn{
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 2px solid teal;
}
</style>
