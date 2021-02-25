<template>
  <el-form ref="form" :model="form" label-position="left" label-width="120px">
  <el-form-item label="First Name">
    <alphabet-input/>
  </el-form-item>
  <el-form-item label="Phone number">
    <el-input v-model="form.phone" :readonly="true"></el-input>
    <el-button class="margin-first" type="primary" @click="incrementNumber">+</el-button>
    <el-button type="primary" @click="decrementNumber">-</el-button>
    <el-button type="primary" @click="generateNumber">Feeling lucky ?</el-button>
  </el-form-item>
  <el-form-item label="Activity zone">
    <el-select v-model="form.region" placeholder="please select your zone">
      <el-option label="Zone one" value="shanghai"></el-option>
      <el-option label="Zone two" value="beijing"></el-option>
    </el-select>
  </el-form-item>
  <el-form-item label="Activity time">
    <el-col :span="11">
      <el-date-picker type="date" placeholder="Pick a date" v-model="form.date1" style="width: 100%;"></el-date-picker>
    </el-col>
    <el-col class="line" :span="2">-</el-col>
    <el-col :span="11">
      <el-time-picker placeholder="Pick a time" v-model="form.date2" style="width: 100%;"></el-time-picker>
    </el-col>
  </el-form-item>
  <el-form-item label="Instant delivery">
    <el-switch style="height: 100%;" v-model="form.delivery"></el-switch>
  </el-form-item>
  <el-form-item label="Activity type">
    <el-checkbox-group v-model="form.type">
      <el-checkbox label="Online activities" name="type"></el-checkbox>
      <el-checkbox label="Promotion activities" name="type"></el-checkbox>
      <el-checkbox label="Offline activities" name="type"></el-checkbox>
      <el-checkbox label="Simple brand exposure" name="type"></el-checkbox>
    </el-checkbox-group>
  </el-form-item>
  <el-form-item label="Resources">
    <el-radio-group v-model="form.resource">
      <el-radio label="Sponsor"></el-radio>
      <el-radio label="Venue"></el-radio>
    </el-radio-group>
  </el-form-item>
  <el-form-item label="Activity form">
    <el-input type="textarea" v-model="form.desc"></el-input>
  </el-form-item>
  <el-form-item>
    <el-button type="primary" @click="onSubmit">Create</el-button>
    <el-button>Cancel</el-button>
  </el-form-item>
</el-form>
</template>

<script>
import AlphabetInput from './AlphabetInput.vue'
export default {
  name: 'FunForm',
  components:{
    AlphabetInput
  },
    data() {
      return {
        form: {
          phone:'0',
          region: '',
          date1: '',
          date2: '',
          delivery: false,
          type: [],
          resource: '',
          desc: ''
        }
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
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