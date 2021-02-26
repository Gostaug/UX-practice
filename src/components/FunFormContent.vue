<template>
  <el-form ref="form" :model="form" label-position="left" label-width="120px">
  <el-form-item label="First Name">
    <alphabet-input @update="setFirstName"/>
  </el-form-item>
  <el-form-item label="Phone number">
    <el-input v-model="form.phone" :readonly="true"></el-input>
    <el-button class="margin-first" type="primary" @click="incrementNumber">+</el-button>
    <el-button type="primary" @click="decrementNumber">-</el-button>
    <el-button type="primary" @click="generateNumber">Feeling lucky ?</el-button>
  </el-form-item>
  <el-form-item label="Birth date">
    <date-slider @update="setBirthDate"/>
  </el-form-item>
  <el-form-item>
    <el-button type="primary" @click="onSubmit">Create</el-button>
    <el-button>Cancel</el-button>
  </el-form-item>
</el-form>
</template>

<script>
import AlphabetInput from './AlphabetInput.vue'
import DateSlider from './DateSlider.vue'
export default {
  name: 'FunForm',
  components:{
    AlphabetInput,
    DateSlider
  },
    data() {
      return {
        form: {
          firstName: '',
          phone:'0',
          birthDate: '',
        }
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
      },
      setFirstName (firstName) {
      this.firstName = firstName;
      },
      setBirthDate (birthDate) {
      this.birthDate = birthDate;
      },
      generateNumber: function () {		
        this.form.phone ='0' + ( Math.floor(Math.random()*899999999) + 100000000); 
      },
      incrementNumber: function () {		
        this.form.phone ='0' + (parseInt(this.form.phone) + 1); 
      } ,  
      decrementNumber: function () {		
        this.form.phone ='0' + (parseInt(this.form.phone) - 1); 
    }
    }  
  }
</script>

<style scoped>
.margin-first{
  margin-left: 10px;
}
.el-form-item  >>> .el-form-item__content {
    display: flex;
    min-height: 40px;
    align-items: center;
} 
</style>