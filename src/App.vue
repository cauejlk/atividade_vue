<script setup>
const books = [
  {
    capa: 'https://m.media-amazon.com/images/I/511XKyPf9-L._AC_UF1000,1000_QL80_.jpg',
    titulo: 'O velho e o menino',
    autor: 'Roberto Tranjan',
    preco: '37.00',
    id: 0,
  },
  {
    capa: 'https://m.media-amazon.com/images/I/81TmOZIXvzL._SL1500_.jpg',
    titulo: 'O Pequeno Príncipe',
    autor: 'Antoine de Saint-Exupéry',
    preco: '15.35',
    id: 1,
  },
  {
    capa: 'https://m.media-amazon.com/images/I/715JOcuqSSL._SL1021_.jpg',
    titulo: 'A metamorfose:',
    autor: 'Franz Kafka ',
    preco: '15.00',
    id: 2,
  },
  {
    capa: 'https://m.media-amazon.com/images/I/7143D7foVmL._SL1500_.jpg',
    titulo: 'Noites brancas',
    autor: 'Fiódor Dostoiévski ',
    preco: '31.80',
    id: 3,
  },
  {
    capa: 'https://m.media-amazon.com/images/I/71yTTLMgq8L._SL1360_.jpg',
    titulo: 'Hamlet',
    autor: 'William Shakespeare',
    preco: '12.30',
    id: 4,
  },
  {
    capa: 'https://m.media-amazon.com/images/I/618-b9Im6dL._SL1457_.jpg',
    titulo: 'Vidas secas',
    autor: 'Graciliano Ramos',
    preco: '16.08',
    id: 5,
  },
  {
    capa: 'https://m.media-amazon.com/images/I/81sblL-t2iL._SL1417_.jpg',
    titulo: 'Declínio de um Homem',
    autor: 'Osamu Dazai',
    preco: '44.12',
    id: 6,
  },
  {
    capa: 'https://m.media-amazon.com/images/I/81ccIcOmAoL._SL1500_.jpg',
    titulo: 'O mito de Sísifo',
    autor: 'Albert Camus',
    preco: '41,87',
    id: 7,
  },
]

</script>

<template>
  <header>
    <nav>
      <ul>
        <li id="logo">IFbooks</li>
        <li id="logo1">Apreço a leitura</li>
        <li id="pesquisar">Pesquisar <span class="fa-solid fa-magnifying-glass"></span></li>
        <li>Termos</li>
        <li>Equipe</li>
        <li>Envio</li>
        <li>Devolução</li>
        <li class="icon"><span class="fa-solid fa-cart-shopping"></span></li>
        <li class="icon" id="mid"><span class="fa-solid fa-heart"></span></li>
        <li class="icon"><span class="fa-solid fa-user"></span></li>
      </ul>
    </nav>
  </header>

  <main>
    <section class="autorDoMes">
      <div class="sobreAutor">
        <p>Autor de Abril</p>
        <h1>Eric-Emanuel Schmitt</h1>
        <p>
          Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and
          in 2001 he received the title of Chevalier des Arts et des Lettres. His books have been
          translated into over 40 languages.
        </p>
        <button>Acessar página do livro</button>
      </div>
      <div class="livro">
        <img src="/public/Schmitt_Nocognia_3D_500pcx 1.jpg" alt="" />
        <p>*within the stock limit</p>
      </div>
    </section>

    <section class="pages">
      <p><span class="fa-solid fa-truck"></span> Frete grátis para SC</p>
      <p id="divisa"><span class="fa-solid fa-star"></span> Livros recomendados</p>
      <p><span class="fa-solid fa-book-open"></span> Mais vendidos</p>
    </section>

    <section class="lancamentos">
      <h3>Lançamentos</h3>
      <div id="books">
        <div v-for="book of books" :key="book.id" class="book">
          <img :src="book.capa" alt="capa do livro"/>
          <h4>{{ book.titulo }}</h4>
          <p id="autor">{{ book.autor }}</p>
          <p id="preco">R$ {{ book.preco }} <span class="fa-regular fa-heart"></span></p>
          <button v-on:click="adicionarAoCarrinho()"><span class="fa-solid fa-cart-shopping"></span> Comprar</button>
        </div>
      </div>
    </section>
  </main>
</template>

<style scoped>
** {
  margin: 0;
  padding: 0;
}
header {
  padding: 2vw 3vw;
  border-bottom: solid #27ae60 2px;
}
header nav ul {
  display: flex;
}

header li {
  list-style: none;
  color: #7b7881;
  margin: 0 2vw;
  padding: 10px;
}

header li#logo {
  font-size: 1.3rem;
  color: black;
  padding: 0 5px 0 0;
  border-right: #27ae60 solid 1.5px;
  margin: 0;
}

header li#logo1 {
  font-family: Arial, Helvetica, sans-serif;
  color: #27ae60;
  margin: 0;
}

header li#pesquisar{
  background-color: #F1F1F1;
  color: #B8B8B8;
  padding: 10px 13px;
  font-size: 1.1rem;
}

header li#pesquisar span{
  color: #7b7881;
  margin: 0 0 0 15vw;
}

header .icon{
  color: #27ae60;
  padding: 10px 1vw;
  margin: 0 0;
  font-size: 1.2rem;
}

header li#mid{
  border-left: #27ae60 solid 1px;
  border-right: #27ae60 solid 1px;
}

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

.pages {
  display: flex;
  justify-content: center;
}
.pages p {
  padding: 2vw 7vw;
  margin: 3vw 0;
  font-size: 1.4rem;
  color: #382c2c;
}
.pages p#divisa {
  border-left: #525252 solid 1px;
  border-right: #525252 solid 1px;
}

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

.lancamentos #books .book img{
  width: auto;
  height: 450px;
}

.lancamentos #books .book h4{
  font-size: 1.3rem;
  padding: 20px 0;
}

.lancamentos #books .book #autor{
  color: #4F4C57;
  padding-bottom: 10px;
}

.lancamentos #books .book #preco{
  font-size: 1.4rem;
  margin: 0 0 10px 0;
  font-family: Arial, Helvetica, sans-serif;
}
.lancamentos #books .book #preco span{
  color: #27ae60;
  margin-left: 10vw;
}

.lancamentos #books .book button{
  border: none;
  background-color: #27ae60;
  color: white;
  font-size: 1.2rem;
  justify-content: center;
  padding: .7vw 6vw;
  border-radius: 3px;
}

</style>
