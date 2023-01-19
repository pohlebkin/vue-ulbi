<template>
    <div
        class="dialog"
        v-if="show === true"
        @click.stop="hideDialog"
    >
        <div @click.stop class="dialog__content">
            <slot></slot>
        </div>
    </div>
</template>

<script>
export default{
    name: 'my-dialog',
    props: {
        show: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        hideDialog(){
            this.$emit('update:show', false);
        }
    }
}
</script>

<style scoped>
.dialog{
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background-color: rgba(0, 0, 0, 0.5);
    position: fixed;
    display: flex;
}

.dialog__content{
    margin: auto;
    background-color: bisque;
    border-radius: 12px;
    min-height: 50px;
    min-width: 50px;
    padding: 20px;
}
</style>
