<template>
  <div class="fun-form">
    <FunFormContent/>
  </div>
</template>
<script>
// @ is an alias to /src
import FunFormContent from '@/components/FunFormContent.vue'

export default {
  name: 'Home',
  components: {
    FunFormContent
  },
}
</script>

<style scoped>

div.fun-form {
  display: flex;
  justify-content: center;
}
</style>