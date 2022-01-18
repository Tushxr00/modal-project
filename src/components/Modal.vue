<template>
    <div class="backdrop" @click="closeModal">
        <div class="modal" :class="{sale : theme === 'sale'}">
            <h1>
                this is the Modal
            </h1>
            <p>
                Modal content
            </p>
            <p>{{ header }}</p>
            <p>{{ text  }}</p>

        </div>
    </div>
</template>

<script>
export default {
    props: ['header','text','theme'],
    methods: {
        closeModal(){
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background-color: white;
        border-radius: 10rem;
    }

    .backdrop{
        top: 0;
        position: fixed;
        background-color: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;
    }
    h1{
        font-size: 2rem;
        color: aqua;
    }
</style>