<template>
    <div class="alphabet-input">
        <div class="container">
            <el-input v-model="myText" :readonly="true"></el-input>
            <el-button type="primary" @click="selectLetter">select</el-button>
            <el-button type="primary" @click="myText = ''">clear</el-button>
        </div>
        <div class="alphabet">
            <div :class="letterClass('a')" >a</div>
            <div :class="letterClass('b')">b</div>
            <div :class="letterClass('c')">c</div>
            <div :class="letterClass('d')">d</div>
            <div :class="letterClass('e')">e</div>
            <div :class="letterClass('f')">f</div>
            <div :class="letterClass('g')">g</div>
            <div :class="letterClass('h')">h</div>
            <div :class="letterClass('i')">i</div>
            <div :class="letterClass('j')">j</div>
            <div :class="letterClass('k')">k</div>
            <div :class="letterClass('l')">l</div>
            <div :class="letterClass('m')">m</div>
            <div :class="letterClass('n')">n</div>
            <div :class="letterClass('o')">o</div>
            <div :class="letterClass('p')">p</div>
            <div :class="letterClass('q')">q</div>
            <div :class="letterClass('r')">r</div>
            <div :class="letterClass('s')">s</div>
            <div :class="letterClass('t')">t</div>
            <div :class="letterClass('u')">u</div>
            <div :class="letterClass('v')">v</div>
            <div :class="letterClass('w')">w</div>
            <div :class="letterClass('x')">x</div>
            <div :class="letterClass('y')">y</div>
            <div :class="letterClass('z')">z</div>
        </div>
    </div>
</template>

<script>
export default {
name: 'AlphabetInput',
data() {
    return {
        myText: '',
        abc: 'abcdefghijklmnopqrstuvwxyz',
        counter : 0,
        isRunning: false,
    }
},
methods: {
    letterClass(letter){
        if(this.abc.charAt(this.counter)==letter){
            return "letter selected"
        }else{
            return "letter"
        }
    },
    selectLetter(){
        this.myText=this.myText + this.abc.charAt(this.counter)
    },
    incrementTime() {
        if(this.counter <24){
            this.counter = parseInt(this.counter) + 1;
        }else{
            this.counter = 0
        }
    },
},
created: function () {
    setInterval(this.incrementTime, 350);
}
}
</script>

<style scoped>


.alphabet-input {
    width: 100%;
}
.container {
    display: flex;
    justify-content: space-between;
}
.alphabet {
    display: flex;
    width: 100%;
    justify-content: center;
}
.letter{
    font-size: 1rem;
    font-weight: bold;
    min-width: 0.8rem;
    height: 2rem;
    margin-bottom: 5px;
}
.selected{
    color: grey;
    border-bottom: 3px solid grey;
}
</style>
