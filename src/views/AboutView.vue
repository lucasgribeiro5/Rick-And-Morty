<template>
  <div class="container">
    <div class="card" style="width: 18rem;">
      <img src="../assets/perfil.jpg" class="img-main" alt="...">
      <div class="card-body">
        <h5 class="card-title">Lucas Garcia Ribeiro</h5>
        <p class="card-text"><b>RA:</b> 1971977</p>
        <p class="card-text"><b>CURSO:</b> Analise e Desenvolvimento de Sistemas</p>
        <p class="card-text"><b>TERMO:</b> 3°</p>
        <p class="card-text"><b>TURMA:</b> B</p>
        <p class="card-text"><b>EMAIL:</b> lucasgarciaribeiro05@gmail.com</p>
        <p class="card-text"><b>CONTATO:</b> (14)99677-0520</p>
      </div>
    </div>
  </div>
  <footer>
    <div class="dados">
      Unimar | ADS | {{ new Date().getFullYear() }}
    </div>
  </footer>
  </template>
  
  <style scoped>
  .container{
    max-width: 19rem;
  }

  card-body{
    width: 680px;
  height: 350px;
  background-color: #ffffff;
  justify-content: center;
  align-items: center;
  margin-top: 100px;
  border-radius: 20px;
  }

  footer{
    background-color:  rgba(19, 35, 47, 0.9); ;
    position:fixed;
    bottom: 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
  }
  </style>