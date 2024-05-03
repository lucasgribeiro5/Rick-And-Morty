<script setup>

const rickandmorty = defineProps(["name","image","gender","status","specie","location","episode"])


</script>

<template>
    <div class="col-md-4">
        <div class="card mb-3">
            <img :src="rickandmorty.image" class="card-img-top" alt="...">
            <div class="card-body">
                <p class="card-title text-center">{{ rickandmorty.name }}</p>
                <p class="card-title text-center">{{ rickandmorty.gender }}</p>
                <p class="card-title text-center">{{ rickandmorty.status }}</p>
                <p class="card-title text-center">{{ rickandmorty.specie }}</p>
                <p class="card-title text-center">{{ rickandmorty.episode.length}}</p>
                <p class="card-title text-center">{{ rickandmorty.location.name }}</p>
            </div>
        </div>
    </div>
</template>

<style>

</style>