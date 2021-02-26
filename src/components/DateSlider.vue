<template>
    <div class="date-slider-container block">
        <div class="slider-input">
            <el-slider @change="emitBirthDate" v-model="dateIndex" :max="50000" :format-tooltip="formatTooltip"></el-slider>
            <div>
                <el-button size="small" @click="dateIndex -= 1">+</el-button>
                <el-button size="small" @click="dateIndex += 1">-</el-button>  
            </div>
        </div>
        <span>{{new Intl.DateTimeFormat('en-GB').format(new Date(birthDate))}}</span>

    </div>
</template>

<script>
export default {
name: 'DateSlider',
data() {
    return {
        today: new Date(),
        birthDate: new Date(),
        dateIndex : 0,
    }
},
methods: {
    emitBirthDate(){
    this.$emit('update', this.birthDate.toString())
    },
    formatTooltip(val) {
        this.birthDate = new Date ();
        this.birthDate.setDate(this.birthDate.getDate() - val)
        return new Intl.DateTimeFormat('en-GB').format(new Date(this.birthDate)) ;
    },
},
}
</script>

<style scoped>
.date-slider-container {
    width: 100%;
}
.space-left{
    margin-left: 10px;
}
.slider-input{
    display: flex;
    justify-content: space-around;
}
.el-slider{
    width: 80%
}
</style>
