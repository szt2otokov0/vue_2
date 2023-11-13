<script setup>
import { ref } from 'vue';
const skills = ref(new Set());
const newSkill = ref(null);
function addSkill(){
    skills.value.add(newSkill.value)
}
function deleteSkill(skill){
    skills.value.delete(skill);
}
</script>

<template>
    <h1>Képességek:</h1>
    <input type="text" v-model="newSkill">
    <button @click="addSkill">Hozzáadás</button><br>
    <div class="card">
        <h3>Képességeim:</h3>
        <div v-for="skill in skills">
            {{skill}}
            <button @click="deleteSkill(skill)">Törlés</button>
        </div>
        
    </div>
</template>