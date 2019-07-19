<template>
    <div class="camera-background">
        
        <video autoplay="true" :srcObject.prop="cameraStream" ></video>

    </div>
</template>

<script>
export default {
    name: "camera",
    data() {
        return {
            cameraStream: undefined 
        } 
    },
    async mounted() {
        if(navigator.mediaDevices.getUserMedia) {
            try {
                let devices = await navigator.mediaDevices.enumerateDevices();
                 
                let cameras = devices.filter(d=>d.kind == "videoinput");
                 
                let stream = await navigator.mediaDevices.getUserMedia({video: { deviceId: { exact: cameras[cameras.length-1].deviceId } }}); 
                 
                this.cameraStream = stream;
            }
            catch(e) {
                console.log(e);
            }
        }
    }
}
</script>

<style scoped>
.camera-background {
    z-index: -1;
    position: fixed;
    height: 100%;
    width: 100%;
    top: 0;
    left: 0;
}
.camera-background video {
    min-width: 100%; 
    min-height: 100%; 
    width: auto; 
    height: auto;
}
</style>