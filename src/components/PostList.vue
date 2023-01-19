<template>
    <div>
        <h2>список постов</h2>
        <post-item
            v-for="post in posts"
            :post="post"
            :key="post.id"
            @remove="$emit('remove', post)"
        />
    </div>
</template>


<script>
import PostItem from '@/components/PostItem.vue';
export default{
    components: { PostItem },
    props: {
        posts: {
            type: Array,
            required: true
        }
    }
}
</script>


<style scoped>

</style>
