<template>
    <div :class="`ion-text-center splash-screen ${showSplashScreen === false ? 'splash-hidden' : ''}`">
        <div class="splash-container ion-text-center">
            <div class="splash-vertical-center ion-text-center">
                <img src="assets/images/icons/my-icon.png" style="height: 100px"/>
                <ion-text color="light">
                    <h4>MyAppTitle</h4>
                </ion-text>
            </div>
        </div>
    </div>
</template>

<script>
    import { 
        defineComponent 
    } from 'vue'
    import {
        IonText
    } from '@ionic/vue';
    export default defineComponent({
        name: 'splashscreen',
        props: {
            showSplashScreen: Boolean
        },
        components: {
            IonText
        }
    })
</script>
<style scoped>
    .splash-screen {
        position: absolute;
        z-index: 9999999999999999;
        background:var(--ion-color-primary);
        width: 100%;
        height: 100%;
    }

    .splash-hidden {
        visibility: hidden;
        opacity: 0;
        transition: visibility 0s 0.5s, opacity 0.5s linear;
    }

    .splash-container {
        height: 100%;
        width: 100%;
        position: relative;
    }

    .splash-vertical-center {
        position: absolute;
        left: 50%;
        top: 50%;
        -webkit-transform: translate(-50%, -50%);
        transform: translate(-50%, -50%);
    }
</style>
