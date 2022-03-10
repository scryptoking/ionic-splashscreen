<template>
    <ion-app>
      <ion-router-outlet />
      <splash-screen :show-splash-screen="showSplashScreen"></splash-screen>
    </ion-app>
</template>
<script>
    import { IonApp, IonRouterOutlet } from '@ionic/vue';
    import {
        defineComponent, ref
    } from 'vue';
    import {
      useRouter
    } from 'vue-router'
    import SplashScreen from './splashScreen.vue'
    export default defineComponent({
      name: 'App',
      setup() {
        const showSplashScreen = ref(false)
        return {
          showSplashScreen
        }
      },
      beforeCreate() {
        this.showSplashScreen = true
      },
      created() {
        this.initOnAppStart();
      },
      methods: {
        initOnAppStart() {
          let myData = this.$store.dispatch("moduleSuite/someProcedure");
          Promise.all([
              myData
          ])
          .then((data) => {
            setTimeout(() => { 
              this.showSplashScreen = false
            }, 2000);
          })
          .catch((error) => {
          
          });
        }
      },
      components: {
        IonApp,
        IonRouterOutlet,
        SplashScreen
      }
    });
</script>
<style>

</style>
