<template lang="">
  <v-app-bar color="gray" :elevation="1">
    <v-app-bar-nav-icon @click="toggleRail"></v-app-bar-nav-icon>
    <v-toolbar-title>Brand</v-toolbar-title>

    <template v-slot:append>
      <v-btn icon="mdi-heart"></v-btn>
      <v-btn icon="mdi-magnify"></v-btn>
      <v-btn icon="mdi-dots-vertical"></v-btn>
    </template>
  </v-app-bar>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    rail: {
      type: Boolean,
      required: true,
    },
    toggleRail: {
      type: Function,
      required: true,
    },
  },
});
</script>
