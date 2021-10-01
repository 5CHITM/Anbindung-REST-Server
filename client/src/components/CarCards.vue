<template>
  <div>
    <div class="d-flex flex-wrap mb-6 justify-center" color="grey lighten-2" flat tile>
      <div v-for="car in cars" :key="car.id" outlined tile class="ma-3 d-flex" width="100%">
        <carCard :car="car" @buycar="buyCar($event)"></carCard>
      </div>
    </div>
  </div>
</template>

<script>
import CarCard from '@/components/CarCard.vue';
export default {
  name: 'CarCards',
  data: () => ({}),

  components: {
    CarCard,
  },
  props: {
    cars: Array,
  },
};
</script>
