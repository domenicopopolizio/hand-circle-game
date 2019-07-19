<template>
    <div class="hand-trigger" v-show="!hasBeenClicked">
        <button @click="clicked"><h3>YOU WON'T REGRET CLICKING ME!</h3></button>
    </div>
</template>

<script>
export default {
    name: 'hand-trigger',
    data() {
        return {
            hasBeenClicked: false
        }
    },
    methods: {
        clicked() {
            this.hasBeenClicked = true;
            this.$emit('click');
        }
    }
}
</script>

<style scoped>
    button {
        margin: 0px;
        padding: 20px;
        width: 60vw;
        max-width: 150px;
        height: 60vw;
        max-height: 150px;
        background-color: red;
        border: 0;
        border-radius: 150px;
        color: white;
        box-shadow: 0px 0px 20px rgba(128, 128, 128, 0.555);
        transition-duration: .15s;
    }
    button:hover {
        cursor: pointer;
    }
    button:active {
        background-color: rgb(211, 1, 1);
    }
</style>