<template>
  <div>
    <div class="d-flex flex-wrap mb-6 justify-center align-stretch" color="grey lighten-2" flat tile>
      <div v-for="car in cars" :key="car.id" outlined tile class="ma-3">
        <carCard :car="car" @buycar="buyCar($event)"></carCard>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import CarCard from '@/components/CarCard.vue';
export default {
  name: 'CarCards',
  data: () => ({}),
  methods: {
    async buyCar(el) {
      try {
        await axios({
          url: `http://127.0.0.1:3000/cars/${el.id}`,
          method: 'patch',
          contentType: 'application/json',
          data: {
            title: `${el.title} RESERVED`,
          },
        });
        return this.$emit('refresh', true);
      } catch (error) {
        console.error(error);
      }
    },
  },
  components: {
    CarCard,
  },
  props: {
    cars: Array,
  },
};
</script>
