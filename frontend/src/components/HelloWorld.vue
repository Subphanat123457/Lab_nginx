<template>
  <div>
    {{ message.message }}
  </div>
</template>

<script>
import axios from 'axios'; // Correct import statement
export default {
  name: 'HelloWorld',
  data() {
    return {
      message: 'Hello, World!'
    }
  },
  mounted() {
    axios.get('http://localhost:3000')
      .then(response => {
        console.log(response.data);
        this.message = response.data;
      })
      .catch(error => {
        console.error('Error fetching data:', error);
      });
  }
}
</script>

<style scoped>
</style>