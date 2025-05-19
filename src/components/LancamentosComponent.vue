<script setup>
defineEmits(['adicionarAoCarrinho'])
defineProps(['books'])
</script>

<template>

  <section class="lancamentos">
    <h3>Lançamentos</h3>
    <div id="books">
      <div v-for="book of books" :key="book.id" class="book">
        <img :src="book.capa" alt="capa do livro" />
        <h4>{{ book.titulo }}</h4>
        <p id="autor">{{ book.autor }}</p>
        <p id="preco">R$ {{ book.preco.replace('.', ',') }} <span class="fa-regular fa-heart"></span></p>
        <button @click="$emit('adicionarAoCarrinho', book)">
          <span class="fa-solid fa-cart-shopping"></span> Comprar
        </button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.lancamentos {
  border-top: #27ae60 solid 2px;
  padding: 5vw 0 0 0;
}

.lancamentos h3 {
  font-size: 2rem;
  margin: 0 0 5vw 2vw;
}

.lancamentos #books {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.lancamentos #books .book {
  margin: 3vw 2vw;
}

.lancamentos #books .book img {
  width: auto;
  height: 450px;
}

.lancamentos #books .book h4 {
  font-size: 1.3rem;
  padding: 20px 0;
}

.lancamentos #books .book #autor {
  color: #4f4c57;
  padding-bottom: 10px;
}

.lancamentos #books .book #preco {
  font-size: 1.4rem;
  margin: 0 0 10px 0;
  font-family: Arial, Helvetica, sans-serif;
}

.lancamentos #books .book #preco span {
  color: #27ae60;
  margin-left: 10vw;
}

.lancamentos #books .book button {
  border: none;
  background-color: #27ae60;
  color: white;
  font-size: 1.2rem;
  justify-content: center;
  padding: 0.7vw 6vw;
  border-radius: 3px;
  cursor: pointer;
}
</style>
