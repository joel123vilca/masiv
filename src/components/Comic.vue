<template>
  <v-container>
    <v-row class="text-center">
      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">{{ info.title }}</h1>
      </v-col>
      <v-col cols="12">
        <v-img :src="info.img" class="my-3" contain height="200" />
      </v-col>
      <v-col>
        <div class="text-center">
          <v-rating v-model="rating"></v-rating>
        </div>
        <v-btn @click="other" text>
          <span class="mr-2">OTRO</span>
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";
export default {
  name: "Comic",
  data: () => ({
    info: {},
    rating: 0,
  }),
  mounted() {
    this.getData();
  },
  methods: {
    async getData() {
      try {
        const id = Math.floor(Math.random() * (700 - 600 + 1) + 600);
        const res = await axios.get(`https://xkcd.com/${id}/info.0.json`);
        this.info = res.data;
      } catch (error) {
        console.log(error);
      }
    },
    other() {
      this.getData();
      this.rating = 0;
    },
  },
};
</script>
