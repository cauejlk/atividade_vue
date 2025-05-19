<script setup>
import HeaderComponent from '@/components/HeaderComponent.vue'
import AutordomesComponent from '@/components/AutordomesComponent.vue'
import PagesComponent from '@/components/PagesComponent.vue'
import LancamentosComponent from '@/components/LancamentosComponent.vue'





import { ref, computed } from 'vue'
const books = [
  {
    capa: 'https://m.media-amazon.com/images/I/511XKyPf9-L._AC_UF1000,1000_QL80_.jpg',
    titulo: 'O velho e o menino',
    autor: 'Roberto Tranjan',
    preco: '37.00',
    id: 0,
    quantidade: 0
  },
  {
    capa: 'https://m.media-amazon.com/images/I/81TmOZIXvzL._SL1500_.jpg',
    titulo: 'O Pequeno Príncipe',
    autor: 'Antoine de Saint-Exupéry',
    preco: '15.35',
    id: 1,
    quantidade: 0
  },
  {
    capa: 'https://m.media-amazon.com/images/I/715JOcuqSSL._SL1021_.jpg',
    titulo: 'A metamorfose:',
    autor: 'Franz Kafka ',
    preco: '15.00',
    id: 2,
    quantidade: 0
  },
  {
    capa: 'https://m.media-amazon.com/images/I/7143D7foVmL._SL1500_.jpg',
    titulo: 'Noites brancas',
    autor: 'Fiódor Dostoiévski ',
    preco: '31.80',
    id: 3,
    quantidade: 0
  },
  {
    capa: 'https://m.media-amazon.com/images/I/71yTTLMgq8L._SL1360_.jpg',
    titulo: 'Hamlet',
    autor: 'William Shakespeare',
    preco: '12.30',
    id: 4,
    quantidade: 0
  },
  {
    capa: 'https://m.media-amazon.com/images/I/618-b9Im6dL._SL1457_.jpg',
    titulo: 'Vidas secas',
    autor: 'Graciliano Ramos',
    preco: '16.08',
    id: 5,
    quantidade: 0
  },
  {
    capa: 'https://m.media-amazon.com/images/I/81sblL-t2iL._SL1417_.jpg',
    titulo: 'Declínio de um Homem',
    autor: 'Osamu Dazai',
    preco: '44.12',
    id: 6,
    quantidade: 0
  },
  {
    capa: 'https://m.media-amazon.com/images/I/81ccIcOmAoL._SL1500_.jpg',
    titulo: 'O mito de Sísifo',
    autor: 'Albert Camus',
    preco: '41.87',
    id: 7,
    quantidade: 0
  },
]


const carrinho = ref([])

const homePage = ref(true)

function adicionarAoCarrinho(book) {
  const itemExistente = carrinho.value.find(item => item.id === book.id)

  if (itemExistente) {
    itemExistente.quantidade++
    alert("add")
  } else {
    carrinho.value.push({
      ...book,
      quantidade: 1
    });alert("add")
  }
}

function diminuirQuantidade(livro) {
  livro.quantidade--
  if (livro.quantidade <= 0) {
    carrinho.value = carrinho.value.filter(item => item.id !== livro.id)
  }
}

const cupom = ref('')
const frete = 0

const totalDoProdutos = computed(() => {
  return carrinho.value.reduce((total, item) => {
    return total + (parseFloat(item.preco) * item.quantidade)
  }, 0)
})
</script>

<template>
  <HeaderComponent @apareceCarrinho="homePage = !homePage" />

  <main v-if="homePage">
    <AutordomesComponent />
    <PagesComponent />
    <LancamentosComponent
    :books= "books"
    @adicionarAoCarrinho = "adicionarAoCarrinho"
    />
  </main>

  <main v-else class="carrinho">
    <section v-if="carrinho.length !== 0" id="carrinho">
      <h1>Carrinho</h1>
      <ul>
        <li>Título</li>
        <li>Quantidade</li>
        <li>Subtotal</li>
      </ul>
      <div v-for="livro of carrinho" :key="livro.id" class="livro">
        <img :src="livro.capa" alt="capa do livro" />
        <div id="titulo">
          <h4>{{ livro.titulo }}</h4>
          <p>{{ livro.autor }}</p>
          <p>R$ {{ livro.preco.replace('.', ',') }}</p>
        </div>
        <div id="quantidade">
          <h5><span @click="livro.quantidade++">+</span> {{ livro.quantidade }} <span
              @click="diminuirQuantidade(livro)">-</span></h5>
        </div>
        <div id="subtotal">
          <h5>R$ {{ (parseFloat(livro.preco) * livro.quantidade).toFixed(2).replace('.', ',') }}</h5>
        </div>
      </div>
    </section>
    <section v-else id="carrinhoVazio">
      <h1>Carrinho está vazio</h1>
    </section>
    <button @click="homePage = !homePage" class="voltarLoja">Voltar para a loja</button>
    <section class="finalizarCompra" v-if="carrinho.length !== 0">
      <div id="cupom">
        <input type="text" v-model="cupom" placeholder="Código do cupom">
        <button>Inserir Cupom</button>
      </div>
      <div id="totalCompras">
        <h3>Total da Comprar</h3>
        <div id="list">
          <div>
            <p>Produtos:</p>
            <p>Frete:</p>
            <p>Total:</p>
          </div>
          <div>
            <p>R$ {{ totalDoProdutos.toFixed(2).replace("." , ",")}}</p>
            <p>Grátis</p>
            <p>R$ {{ (totalDoProdutos + frete).toFixed(2).replace("." , ",") }}</p>
          </div>
        </div>
        <button>Ir para o pagamento</button>
      </div>
    </section>
  </main>
</template>

<style scoped>
** {
  margin: 0;
  padding: 0;
}

.carrinho h1 {
  margin: 2vw 0 0 10vw;
  font-family: Arial, Helvetica, sans-serif;
}

.carrinho #carrinho ul {
  display: flex;
  list-style: none;
  font-family: Arial, Helvetica, sans-serif;
  justify-content: space-between;
  border-bottom: #27ae60 2px solid;
}

.carrinho ul li {
  font-size: 1.3rem;
  padding: 5vw 10vw 1vw 10vw;
}

.carrinho .livro {
  display: grid;
  grid-template-columns: 150px 190px 1165px 150px;
  align-items: center;
  gap: 1rem;
  padding: 1rem;
  border-bottom: 1px solid #ccc;
}

.carrinho .livro img {
  width: auto;
  height: 220px;
  margin: 0 30px 0 0;
}

.carrinho .livro h4 {
  font-size: 1.3rem;
  margin: -3vw 0 0 0;
}

.carrinho .livro p:first-of-type {
  font-family: Arial, Helvetica, sans-serif;
  color: #4F4C57;
  font-size: 1.1rem;
  margin: 15px 0;
}

.carrinho .livro p:last-of-type {
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.3rem;
}

.carrinho .livro #quantidade {
  font-size: 1.6rem;
  margin: 0 31vw 0 23vw;
  font-family: 'Courier New', Courier, monospace;
  border: #4F4C57 1px solid;
  padding: .5vw 1.55vw;
}

.carrinho .livro #quantidade span {
  padding: 0 5px;
  cursor: pointer;
}

.carrinho .livro #subtotal {
  font-size: 1.6rem;
  font-family: 'Courier New', Courier, monospace;
}

.carrinho #carrinhoVazio {
  font-size: 1.4rem;
}

.voltarLoja{
  background-color: #27ae60;
  color: white;
  padding: 10px 20px;
  border: none;
  font-size: 1.1rem;
  margin: 10px 0;
  border-radius: 5px;
  cursor: pointer;
}

.finalizarCompra #cupom{
  margin: 0 4vw;
}

.finalizarCompra #cupom input{
  font-size: 1.1rem;
  margin-right: 10px;
  padding: 7px;
}

.finalizarCompra #cupom button{
  font-size: 1rem;
  background-color: #27ae60;
  border: none;
  color: white;
  padding: 10px 20px;
  cursor: pointer;
}

.finalizarCompra{
  font-size: 1.1rem;
  font-family: Arial, Helvetica, sans-serif;
  margin: 10px 35vw;
}

.finalizarCompra #totalCompras{
  border: #4d4c4c 1.5px solid;
  border-radius: 5px;
  margin: 15px 0;
  padding: 10px 20px;
}

.finalizarCompra #totalCompras #list{
  display: flex;
  justify-content: space-between;
}

.finalizarCompra #totalCompras #list p{
  margin: 13px 0;
}

.finalizarCompra #totalCompras button{
  border: none;
  background-color: #27ae60;
  color: white;
  padding: 20px 30px;
  font-size: 1.3rem;
  border-radius: 10px;
  margin-left: 7vw ;
  cursor: pointer;
}

</style>
