<script setup>
import {ref} from 'vue';
const szoveg = ref("banán");
const azonosito = ref("majom");
const text = ref(null);
const validPwd = ref(false);
const osztaly = ref("card")
const fruits = ref(["alma","körte","barack","paradicsom"])
function changeColor(){
    azonosito.value = "sarga";
}
const save = () => {
    console.log(text.value);
    validPwd.value = text.value.length > 5
}
</script>
<template>
    <h1 v-bind:id="azonosito">Vue form?</h1>
    <p :class="osztaly">{{ szoveg }}</p>
    <button @click="changeColor">Válts színt</button>
    {{ 5+ 2}}
    <input type="text" v-model="text">
    <button @click="save">Mentés</button>
    <p v-if="validPwd">Jó jelszó</p>
    <p v-else="validPwd">Túl rövid a jelszó</p>
    <p v-for="fruit in fruits">{{ fruit }}</p>
</template>

<style scoped></style>