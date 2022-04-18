<template>
  <div class="app">
    <BacilusList :BacilusList="bacterias" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import BacilusList from "./components/BacilusList.vue";
import Bacilus from "./types/Bacilus";

export default defineComponent({
  name: "App",
  components: { BacilusList },
  setup() {
    const bacterias = ref<Bacilus[]>([
      {
        name: "Bacteria 1",
        description: "Ta chikita",
        source:
          "https://phantom-marca.unidadeditorial.es/252acdd64f48851f815c16049a789f23/resize/1320/f/jpg/assets/multimedia/imagenes/2021/04/19/16188479459744.jpg",
        id: 1,
      },
      {
        name: "Bacteria 2",
        description: "Ta chikita",
        source:
          "https://phantom-marca.unidadeditorial.es/252acdd64f48851f815c16049a789f23/resize/1320/f/jpg/assets/multimedia/imagenes/2021/04/19/16188479459744.jpg",
        id: 2,
      },
      {
        name: "Bacteria 3",
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

    return { bacterias };
  },

  methods: {},
});
</script>

<style>
</style>
