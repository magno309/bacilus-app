<template>
  <p class="order">Ordenado por {{ order }}</p>
  <div class="bacilus-list">
    <b-card
      v-for="bacilus in BacilusList"
      :key="bacilus.id"
      :title="bacilus.name"
      :img-src="bacilus.source"
      img-alt="Image"
      img-top
      tag="article"
      class="bacilus-list-item"
    >
      <b-card-text>
        {{ bacilus.description }}
      </b-card-text>
    </b-card>
  </div>
</template>

<script lang="ts">
import Bacilus from "@/types/Bacilus";
import OrderTerm from "@/types/OrderTerm";
import { computed, defineComponent, PropType } from "vue";

export default defineComponent({
  components: {},
  props: {
    BacilusList: {
      required: true,
      type: Array as PropType<Bacilus[]>,
    },
    order: {
      required: true,
      type: String as PropType<OrderTerm>,
    },
  },
  setup(props) {
    const orderedBacilus = computed(() => {
      return [...props.BacilusList].sort((a: Bacilus, b: Bacilus) => {
        return a[props.order] > b[props.order] ? 1 : -1;
      });
    });

    return{ orderedBacilus };
  },
});
</script>

<style scoped>
.order {
  max-width: 90%;
  margin: 40px auto;
}
</style>
