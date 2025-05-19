<template>
  <section class="autorDoMes">
      <div class="sobreAutor">
        <p>Autor de Abril</p>
        <h1>Eric-Emanuel Schmitt</h1>
        <p>
          Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and
          in 2001 he received the title of Chevalier des Arts et des Letres. His books have been
          translated into over 40 languages.
        </p>
        <button>Acessar página do livro</button>
      </div>
      <div class="livro">
        <img src="/public/Schmitt_Nocognia_3D_500pcx 1.jpg" alt="" />
        <p>*within the stock limit</p>
      </div>
    </section>
</template>

<style scoped>

.autorDoMes {
  display: flex;
  align-items: center;
  padding: 0 10vw 3vw 10vw;
  border-bottom: #27ae60 solid 2px;
}

.autorDoMes img {
  height: 600px;
}

.autorDoMes div.sobreAutor p:first-of-type {
  color: #27ae60;
  border: #27ae60 solid 2px;
  padding: 0.7vw 1vw;
  border-radius: 5px;
  margin: 10vw 41vw 0 0;
  font-family: Arial, Helvetica, sans-serif;
}

.autorDoMes div.sobreAutor h1 {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 3.6rem;
  margin: 2vw 0;
}

.autorDoMes div.sobreAutor p:last-of-type {
  padding: 0 14vw 2vw 0;
  color: #4d4c4c;
  font-size: 1.2rem;
}

.autorDoMes .sobreAutor button {
  border: 0;
  background-color: #27ae60;
  color: white;
  padding: 10px 20px;
  border-radius: 3px;
  font-size: 1.2rem;
}

.autorDoMes .livro {
  padding: 3vw 5vw 0 0;
}

.autorDoMes .livro p {
  margin-top: -4vw;
  text-align: end;
}
</style>
