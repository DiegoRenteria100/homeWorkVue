<template>
  <div>
      <home-component v-if="isOnline()"></home-component>
      <home-offline v-else></home-offline>
    </div>
</template>

<script>
import HomeComponent from './components/HomeComponent.vue';
import HomeOffline from './components/HomeOffline.vue';

export default {
  name: 'App',
  components: {
    HomeComponent,
    HomeOffline,
  },
  data() {
    return {
    }
  },
  mounted() {
  },
  methods: {
    isOnline(){
      return window.navigator.onLine;
    }
  },
}
</script>

<style>
body{
  background-color: rgb(192, 231, 251);
  margin: 0;
}
</style>
