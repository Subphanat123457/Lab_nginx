<template>
  <div class="home">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  }
}
</script>

<style scoped>
.home {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh; /* ให้เต็มความสูงของ viewport */
}
</style>
