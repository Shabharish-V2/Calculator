<template>
    <div id="calc">
        <div class="screen">{{ screen }}</div>


        <div @click="concatNum('1')" class="btn num">1</div>
        <div @click="concatNum('2')" class="btn num">2</div>


        <div @click="concatNum('3')" class="btn num">3</div>
        <div @click="concatNum('4')" class="btn num">4</div>


        <div @click="concatNum('5')" class="btn num">5</div>
        <div @click="concatNum('6')" class="btn num">6</div>

        <div @click="concatNum('7')" class="btn num">7</div>
        <div @click="concatNum('8')" class="btn num">8</div>


        <div @click="concatNum('9')" class="btn num">9</div>

        <div @click="concatNum('0')" class="btn num">0</div>
        <div @click="concatNum('.')" class="btn num">.</div>

        <div @click="evaluate()" class='btn equal'>=</div>
        <div @click="concatOP('*')" class="btn num">*</div>
        <div @click="concatOP('%')" class="btn num">%</div>
        <div @click="concatOP('/')" class="btn num">/</div>
        <div @click="concatOP('-')" class="btn num">-</div>
        <div @click="concatOP('+')" class="btn num">+</div>
        <div @click="clear()" class='btn clear'>C</div>
    </div>
</template>


<script setup>
import { ref } from 'vue';
let screen = ref(0);
const concatNum=(num)=>{
   screen.value === 0? (screen.value=num) : (screen.value += num);
}
const concatOP=(OP)=>{
    if(screen.value === 0 || screen.value === "."){
        if(OP == '-'){
            screen.value = OP;
            return;
        } else {
            return;
        }
    }
    screen.value += OP;
}
const clear=()=>{
    screen.value=0;
}
const evaluate=()=>{
     screen.value = eval(screen.value);
}

</script>


  




<style scoped lang="scss">
@import "@/components/styles/MyCalculator.scss";
</style>