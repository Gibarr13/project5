<template>
<div class="flex justify-center gap-6 p-10">

    <button @click="prevPage" :disabled="activePage === 1" class="rounded-md bg-slate-100 p-4 font medium text-slate-900 shadow-emerald-300">PREV</button>

    <button v-for="page in pages" :key="page" class="rounded-md bg-slate-100 p-4 font medium text-slate-900 shadow-emerald-300" :class="page === activePage ? 'bg-yellow-300 text-slate-100': ''"> {{ page }}</button>

    <button @click="nextPage" :disabled="activePage === pages" class="rounded-md bg-slate-100 p-4 font medium text-slate-900 shadow-emerald-300">NEXT</button>

</div>

</template>

<script setup>
import { ref } from 'vue'
const pages = ref(12)
const activePage = ref(3)

const prevPage = () => {
    if (activePage.value > 1) {
        activePage.value--
    }

    console.log(activePage)
}

const nextPage = () => {
    if (activePage.value < pages.value) {
        activePage.value++
    }

    console.log(activePage)
}

console.log(activePage)

</script>