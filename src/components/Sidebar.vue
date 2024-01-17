<template>
  <v-navigation-drawer :rail="rail">
    <v-sheet color="grey-lighten-4" :class="[!rail ? 'pa-4' : 'pa-2']">
      <div class="text-center">
        <v-avatar v-if="!rail" class="mb-4" color="grey-darken-1" size="64">
          <v-img
            width="100%"
            height="100%"
            cover
            alt="Avatar"
            :src="img"
          ></v-img>
        </v-avatar>
        <v-avatar v-else class="mb-4" color="grey-darken-1" size="32">
          <v-img alt="Avatar" cover :src="img"></v-img>
        </v-avatar>
      </div>

      <div class="text-center">
        <template v-if="!rail">
          <h2>Rofiyev Dilshod</h2>
          <span>rofiyevdilshod@gmail.com</span>
        </template>
        <template v-else>
          <h2>R.D</h2>
        </template>
      </div>
    </v-sheet>

    <v-divider></v-divider>

    <v-list>
      <v-list-item
        v-for="[icon, text] in links"
        :key="icon"
        :prepend-icon="icon"
        :title="text"
        link
      ></v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Sidebar",
  props: {
    rail: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      links: [
        ["mdi-microsoft-windows", "Dashboard"],
        ["mdi-account", "Profile"],
        ["mdi-clipboard-list-outline", "Products"],
        ["mdi-clipboard-list", "Orders"],
        ["mdi-cog-outline", "Settings"],
      ] as string[][],
      img: "data:image/jpeg;base64,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" as string,
    };
  },
});
</script>
