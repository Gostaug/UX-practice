<template>
  <div class="tilting-box">
        <el-button type="primary" @click="open">Skip</el-button>
  </div>
</template>

<script>
export default {
  name: 'TiltingBox',
  methods: {
      open() {
        this.$alert('This is a message', 'Title', {
          confirmButtonText: 'OK',
          callback: action => {
            this.$message({
              type: 'info',
              message: `action: ${ action }`
            });
          }
        });
      }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
