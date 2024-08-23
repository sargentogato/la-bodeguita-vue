<template>
  <h1 class="title text-center">I nostri menù</h1>
  <h5 class="subtitle">
    !!!!!!Assaggiate i nostri menù completi: bevanda (sangrìa), antipasto,
    paella e dolce o ordinate le nostre paellas che portiamo direttamente da
    voi!!! Tutto a domicilio!!!
  </h5>
  <div class="menu">
    <h3 class="text-center">Menù completi</h3>
    <ol class="d-flex flex-column gap-2">
      <li class="item">
        Paella Valenciana: sangrìa, 3 antipasti, paella di pollo e verdure e
        dolce valenciano. Min. 4 persone
      </li>
      <li class="item">
        Paella di Pesce ( marisco): sangrìa, 3 antipasti, paella di pesce e
        dolce valenciano.min 4 persone
      </li>
      <li class="item">
        Paella di verdure: sangrìa, 3 antipasti, paella di verdure (stagione) e
        dolce valenciano.min 4 persone
      </li>
      <li class="item">
        Paella vegana: sangrìa, 3 antipasti, paella di tofu/funghi e dolce
        valenciano
      </li>
      <sub class="sub">Min 4 persone.</sub>
    </ol>
  </div>
  <div class="paellas">
    <h3 class="text-center">Paellas</h3>
    <ol class="d-flex flex-column gap-2">
      <li class="item">
        <strong>Paella Valenciana:</strong>pollo e verdure, zafferano e
        rosmarino, riso bomba
      </li>
      <li class="item">
        Paella di Pesce ( marisco): pesce e verdure, zafferano, riso bomba
      </li>
      <li class="item">
        Paella di Verdure: verdure di stagione, zafferano, riso bomba
      </li>
      <li class="item">
        Paella Vegana: Tofu/funghi, riso integrale/avena/ o riso bomba.
      </li>
    </ol>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.title,
.subtitle,
.menu,
.paellas {
  color: white;
}

.item {
  list-style-type: number;
}

.sub {
  bottom: 0;
  font-weight: bold;
}
</style>
