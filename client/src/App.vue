<template>
  <v-app>
    <LogoBar></LogoBar>
    <v-main>
      <router-view :cars="cars" @refresh="getCars()"></router-view>
    </v-main>
  </v-app>
</template>

<script>
import axios from 'axios';
import LogoBar from '@/components/LogoBar.vue';
export default {
  name: 'App',

  data: () => ({
    cars: [],
  }),
  methods: {
    async getCars() {
      console.log('Get Cars');
      try {
        const { data } = await axios({
          url: `http://127.0.0.1:3000/cars`,
          method: 'GET',
        });
        this.cars = data;
      } catch (error) {
        console.error(error);
      }
    },
  },
  created() {
    this.getCars();
  },
  components: {
    LogoBar,
  },
};
</script>
