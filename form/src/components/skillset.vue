<script setup>
import { ref } from 'vue';
const skills = ref([]);
const newSkill = ref(null);
function addSkill(){
    skills.value.push(newSkill.value)
}
function clearSkills(){
    skills.value = [];
}
</script>

<template>
    <h1>Képességek:</h1>
    <input type="text" v-model="newSkill">
    <button @click="addSkill">Hozzáadás</button>
    <button @click="clearSkills">Kiürítés</button>
    <div class="card">
        <h3>Képessgeim:</h3>
        <div v-for="skill in skills">{{skill}}</div>
    </div>
</template>