<script setup>
defineEmits(['apareceCarrinho'])

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
        <li class="icon" @click="$emit('apareceCarrinho')">
          <span class="fa-solid fa-cart-shopping"></span>
        </li>
        <li class="icon" id="mid"><span class="fa-solid fa-heart"></span></li>
        <li class="icon"><span class="fa-solid fa-user"></span></li>
      </ul>
    </nav>
  </header>
</template>

<style scoped>

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

header li#pesquisar {
  background-color: #f1f1f1;
  color: #b8b8b8;
  padding: 10px 13px;
  font-size: 1.1rem;
}

header li#pesquisar span {
  color: #7b7881;
  margin: 0 0 0 15vw;
}

header .icon {
  color: #27ae60;
  padding: 10px 1vw;
  margin: 0 0;
  font-size: 1.2rem;
  cursor: pointer;
}

header li#mid {
  border-left: #27ae60 solid 1px;
  border-right: #27ae60 solid 1px;
}
</style>
