<script setup>
import { onMounted, reactive, ref } from 'vue';
import RickandMorty from '../components/RickandMorty.vue';

let listapersonagens = reactive(ref());
let types = reactive(ref());

onMounted(() => {
  fetch("https://rickandmortyapi.com/api/character")
  .then(response => response.json())
  .then(response => {
    listapersonagens.value = response.results;
    console.log(listapersonagens);
  });
});



</script>

<template>
  <main>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-12 col-md-12">
          <div class="card">
            <div class="card-body row" style="background-color: #081119;">
              <RickandMorty
                v-for="rickandmorty in listapersonagens"
                :key="rickandmorty.id"
                :name="rickandmorty.name"
                :image="rickandmorty.image"
                :status="rickandmorty.status"
                :species="rickandmorty.species"
                :gender="rickandmorty.gender"
                :location="rickandmorty.location"
                :episode="rickandmorty.episode"
              ></RickandMorty>
            </div>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>

<style>
body{
  background-color: #081119;
}

.card {
  margin-top: 0;
  padding-top: 0;
}


.card-body .rickandmorty {
  flex: 0 0 calc(25% - 10px);
  margin-bottom: 10px;
}

.rickandmorty img {
  width: 100%;
  border-radius: 5px;
}

.rickandmorty .info {
  margin-top: 5px;
  text-align: center;
}

.container::-webkit-scrollbar {
  width: 10px;
  height: 10px;
}

.container::-webkit-scrollbar-track {
  background: #f1f1f1;
}

.container::-webkit-scrollbar-thumb {
  background: #888;
  border-radius: 5px;
}

.container::-webkit-scrollbar-thumb:hover {
  background: #555;
}
</style>