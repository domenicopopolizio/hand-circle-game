<template>
    <div class="hand" :class="{'out':isOut}">
        <div class="hand-shape" >
        </div>
    </div>
</template>

<script>
export default { 
    name: 'hand',
    props: {
        isOut: Boolean
    }
}
</script>

<style scoped>
    .hand {
        position: absolute;
        bottom: 0; 
        left: -400px;
        transition-duration: 1s;
    }
    .hand-shape {
        width: 80vw;
        height: 80vh;
        max-width: 400px;
        max-height: 500px;
        background-image: url('../assets/hand.png');
        background-size: contain;
        background-repeat: no-repeat;
        background-position: bottom left;
        
    }
    .out {
        left: 0px;
    }
</style>