<template>
  <nav>
    <v-app-bar flat app color="#fff">
      <v-app-bar-nav-icon
        @click="drawer = !drawer"
        color="grey"
      ></v-app-bar-nav-icon>
    </v-app-bar>

    <v-navigation-drawer app v-model="drawer" light>
      <v-layout column class="logo_dash">
        <v-avatar rounded="62" size="70"><img src="/v.png" /></v-avatar>
      </v-layout>
      <v-list dense>
        <v-list-item-group v-model="selectedItem" color="#4B0082">
          <v-list-item v-for="(item, i) in items" :key="i" router :to="item.to">
            <v-list-item-icon>
              <v-icon left v-text="item.icon"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title
                color="#000"
                v-text="item.title"
              ></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
  </nav>
</template>
<script>
export default {
  data() {
    return {
      selectedItem: "",
      drawer: false,
      items: [
        {
          icon: "mdi-book-open-variant",
          title: "Product Catalog",
          to: "/product_catalog",
        },
        {
          icon: "mdi-playlist-edit",
          title: "Product Instructions",
          to: "/product_instructions",
        },
        {
          icon: "mdi-calculator-variant",
          title: "Product Calculator",
          to: "/product_calculator",
        },
      ],
    };
  },
};
</script>
<style>
.nuxt-logo {
  height: 180px;
}
.logo_dash {
  margin-top: 5px;
  align-items: center;
}
</style>
