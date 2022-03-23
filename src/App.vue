<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-btn href="" text>
        <span class="mr-2">Comics</span>
      </v-btn>
    </v-app-bar>

    <v-main>
      <Comic />
    </v-main>
  </v-app>
</template>

<script>
import Comic from "./components/Comic";

export default {
  name: "App",

  components: {
    Comic,
  },
};
</script>
