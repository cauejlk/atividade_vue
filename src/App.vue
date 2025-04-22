<script setup>
  const books = [
    {
    capa: 'https://m.media-amazon.com/images/I/511XKyPf9-L._SL1000_.jpg',
    titulo: 'O velho e o menino',
    autor: 'Roberto Tranjan',
    preco: '37.00',
    id: 0
    },
    {
    capa: 'https://m.media-amazon.com/images/I/81TmOZIXvzL._SL1500_.jpg',
    titulo: 'O Pequeno Príncipe',
    autor: 'Antoine de Saint-Exupéry',
    preco: '15.35',
    id: 1
    },
    {
    capa: 'https://m.media-amazon.com/images/I/715JOcuqSSL._SL1021_.jpg',
    titulo: 'A metamorfose:',
    autor: 'Franz Kafka ',
    preco: '15.00',
    id: 2
    },
    {
    capa: 'https://m.media-amazon.com/images/I/7143D7foVmL._SL1500_.jpg',
    titulo: 'Noites brancas',
    autor: 'Fiódor Dostoiévski ',
    preco: '31.80',
    id: 3
    },
    {
    capa: 'https://m.media-amazon.com/images/I/71yTTLMgq8L._SL1360_.jpg',
    titulo: 'Hamlet',
    autor: 'William Shakespeare',
    preco: '12.30',
    id: 4
    },
    {
    capa: 'https://m.media-amazon.com/images/I/618-b9Im6dL._SL1457_.jpg',
    titulo: 'Vidas secas',
    autor: 'Graciliano Ramos',
    preco: '16.08',
    id: 5
    },
    {
    capa: 'https://m.media-amazon.com/images/I/81sblL-t2iL._SL1417_.jpg',
    titulo: 'Declínio de um Homem',
    autor: 'Osamu Dazai',
    preco: '44.12',
    id: 6
    },
    {
    capa: 'https://m.media-amazon.com/images/I/81ccIcOmAoL._SL1500_.jpg',
    titulo: 'O mito de Sísifo',
    autor: 'Albert Camus',
    preco: '41,87',
    id: 7
    },
  ]
</script>

<template>
  <header>
    <nav>
      <ul>
        <li id="logo">IFbooks</li>
        <li id="logo1">Apreço a leitura</li>
        <li id="pesquisar">Pesquisar</li>
        <li>Termos</li>
        <li>Equipe</li>
        <li>Envio</li>
        <li>Devolução</li>
        <li class="icon">Carrinho</li>
        <li class="icon">Curtidos</li>
        <li class="icon">Perfil</li>
      </ul>
    </nav>
  </header>

  <main>
    <section>
      <div>
        <p>Autor de Abril</p>
        <h1>Eric-Emanuel Schmitt</h1>
        <p>Eric-Emmanuel Schmitt has been awarded more than 20 literary prizes and distinctions, and in 2001 he received the title of Chevalier des Arts et des Lettres. His books have been translated into over 40 languages.</p>
        <button>Acessar página do livro</button>
      </div>
      <div>
        <img src="/public/Schmitt_Nocognia_3D_500pcx 1.jpg" alt="">
        <p>*within the stock limit</p>
      </div>
    </section>
    <section>
      <p>Frete grátis para SC</p>
      <p>Livros recomendados</p>
      <p>Mais vendidos</p>
    </section>
    <section>
      <h3>Lançamentos</h3>
      <div v-for="book of books" :key="book.id">
        <img :src="book.capa" alt="capa do livro">
        <h4>{{ book.titulo }}</h4>
        <p>{{ book.autor }}</p>
        <p>R${{ book.preco }} </p>
        <button>Comprar</button>
      </div>
    </section>
  </main>
</template>

<style scoped>
**{
  margin: 0;
  padding: 0;
}

header nav ul{
  display: flex;
}

li{
  list-style: none;
  color: #7B7881;
}

li#logo{
  font-size: 1.3rem;
}


</style>
