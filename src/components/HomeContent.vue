<template>
  <div class="home-content">
    <el-button type="primary" @click="goToForm">Not so nice form</el-button>
    <TiltingBox/>
  </div>
</template>

<script>
import TiltingBox from './TiltingBox.vue'
export default {
  name: 'HomeContent',
  components: {
    TiltingBox
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
