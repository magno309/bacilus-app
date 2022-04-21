<template>
  <div class="app">
    <header>
      <div class="order">
        <b-button
          variant="light"
          style="margin: 0 10px"
          @click="handleClick('name')"
          >Ordenar por nombre</b-button
        >
        <b-button
          variant="light"
          style="margin: 0 10px"
          @click="handleClick('id')"
          >Ordenar por ID</b-button
        >
      </div>
    </header>
    <BacilusList :BacilusList="bacterias" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import BacilusList from "./components/BacilusList.vue";
import Bacilus from "./types/Bacilus";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
  name: "App",
  components: { BacilusList },
  setup() {
    const bacterias = ref<Bacilus[]>([
      {
        name: "Bacteria 3",
        description: "Ta chikita",
        source:
          "https://phantom-marca.unidadeditorial.es/252acdd64f48851f815c16049a789f23/resize/1320/f/jpg/assets/multimedia/imagenes/2021/04/19/16188479459744.jpg",
        id: 1,
      },
      {
        name: "Acteria 2",
        description: "Ta chikita",
        source:
          "https://phantom-marca.unidadeditorial.es/252acdd64f48851f815c16049a789f23/resize/1320/f/jpg/assets/multimedia/imagenes/2021/04/19/16188479459744.jpg",
        id: 2,
      },
      {
        name: "Bacteria 1",
        description:
          "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dolores eaque itaque ducimus eius nesciunt ratione, quasi aliquid debitis explicabo vel aperiam corrupti eveniet eos ipsam, similique quos animi dicta porro.",
        source:
          "https://phantom-marca.unidadeditorial.es/252acdd64f48851f815c16049a789f23/resize/1320/f/jpg/assets/multimedia/imagenes/2021/04/19/16188479459744.jpg",
        id: 3,
      },
      {
        name: "Bacteria 4",
        description: "Ta chikita",
        source:
          "https://phantom-marca.unidadeditorial.es/252acdd64f48851f815c16049a789f23/resize/1320/f/jpg/assets/multimedia/imagenes/2021/04/19/16188479459744.jpg",
        id: 4,
      },
      {
        name: "Bacteria 5",
        description: "Ta chikita",
        source:
          "https://phantom-marca.unidadeditorial.es/252acdd64f48851f815c16049a789f23/resize/1320/f/jpg/assets/multimedia/imagenes/2021/04/19/16188479459744.jpg",
        id: 5,
      },
    ]);

    const order = ref<OrderTerm>("id");

    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { bacterias, handleClick, order };
  },

  methods: {},
});
</script>

<style scoped>
header {
  text-align: center;
}

header .order {
  margin-top: 20px;
}
</style>>
