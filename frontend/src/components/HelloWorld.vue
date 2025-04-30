<template>
  <div>
    <div v-if="errorMessage">
      {{ errorMessage }}
    </div>
    <div v-else>
      {{ message.message }}
    </div>
  </div>
</template>

<script>
import axios from 'axios'; // Correct import statement
export default {
  name: 'HelloWorld',
  data() {
    return {
      message: 'Hello, World!',
      errorMessage: '' // ตัวแปรสำหรับเก็บข้อความข้อผิดพลาด
    }
  },
  mounted() {
    axios.get('http://localhost/api')
      .then(response => {
        console.log(response.data);
        this.message = response.data;
      })
      .catch(error => {
        console.error('Error fetching data:', error);
        this.errorMessage = 'โหลดข้อมูลไม่สำเร็จ'; // ข้อความแสดงข้อผิดพลาด
      });
  }
}
</script>

<style scoped>
</style>