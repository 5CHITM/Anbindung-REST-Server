<template>
  <v-app-bar app color="white" elevate-on-scroll height="200">
    <v-row>
      <v-col cols="2"> </v-col>
      <v-col class="d-flex justify-space-around">
        <v-app-bar-title>
          <v-img src="logo.png" max-height="150" contain></v-img>
        </v-app-bar-title>
      </v-col>
      <v-col cols="2" class="d-flex justify-end"> </v-col>
    </v-row>
  </v-app-bar>
</template>

<script>
export default {
  name: 'LogoBar',
  data: () => ({
    //
  }),
};
</script>
