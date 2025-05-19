<template>
    <section class="pages">
      <p><span class="fa-solid fa-truck"></span> Frete grátis para SC</p>
      <p id="divisa"><span class="fa-solid fa-star"></span> Livros recomendados</p>
      <p><span class="fa-solid fa-book-open"></span> Mais vendidos</p>
    </section>
</template>

<style scoped>

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
</style>
