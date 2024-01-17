<template>
  <v-app id="inspire">
    <SidebarComponent :rail="rail" />

    <v-main>
      <HeaderComponent :rail="rail" :toggleRail="toggleRail" />

      <v-container class="py-8 px-6" fluid>
        <v-row>
          <v-col v-for="card in cards" :key="card" cols="12">
            <v-card>
              <v-list lines="two">
                <v-list-subheader :title="card"></v-list-subheader>

                <template v-for="n in 6" :key="n">
                  <v-list-item>
                    <template v-slot:prepend>
                      <v-avatar color="grey-darken-1"></v-avatar>
                    </template>

                    <v-list-item-title
                      color="primary"
                      :title="`Message ${n}`"
                    ></v-list-item-title>

                    <v-list-item-subtitle
                      color="primary"
                      title="Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil repellendus distinctio similique"
                    ></v-list-item-subtitle>
                  </v-list-item>

                  <v-divider
                    v-if="n !== 6"
                    :key="`divider-${n}`"
                    inset
                  ></v-divider>
                </template>
              </v-list>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
import HeaderComponent from "@/components/Header.vue";
import SidebarComponent from "@/components/Sidebar.vue";

export default {
  name: "App",
  components: { HeaderComponent, SidebarComponent },
  data: () => ({
    cards: ["Today", "Yesterday"] as string[],
    rail: false as boolean,
  }),
  methods: {
    toggleRail() {
      this.rail = !this.rail;
    },
  },
};
</script>
