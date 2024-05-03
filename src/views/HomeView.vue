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
.card-body {
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
</style>