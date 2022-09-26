<template>
  <v-app>
    <v-toolbar app>
      <!-- <span class="hidden-sm-and-up">
        <v-toolbar-side-icon @click="sidebar = !sidebar"> </v-toolbar-side-icon>
      </span> -->
      <v-toolbar-title>
        <!-- <router-link to="/" tag="span" style="cursor: pointer"> -->
        Hello
        <!-- </router-link> -->
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <v-toolbar-items class="hidden-xs-only">
        <v-menu open-on-hover v-for="item in nav" :key="item.title">
          <template v-slot:activator="{ props }">
            <v-btn flat :to="item.path" v-bind="props">
              <v-icon left dark>{{ item.icon }}</v-icon>
              {{ item.title }}
            </v-btn>
          </template>

          <v-list>
            <v-list-item v-for="(item, index) in items" :key="index">
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-toolbar-items>
    </v-toolbar>

    <!-- <v-menu
      open-on-hover
    >
      <template v-slot:activator="{ props }">
        <v-btn
          color="primary"
          v-bind="props"
        >
          Dropdown
        </v-btn>
      </template>

      <v-list>
        <v-list-item
          v-for="(item, index) in items"
          :key="index"
        >
          <v-list-item-title>{{ item.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-menu> -->

    <v-main>
      <slot />
    </v-main>
  </v-app>
</template>
  
<script>
export default {
  data() {
    return {
      nav: [
        {
          icon: "home",
          text: "Home",
          title: "Back to Home page",
          active: true,
        },
        {
          icon: "info",
          text: "About",
          title: "About this demo",
          active: false,
        },
        {
          icon: "assignment_turned_in",
          text: "Todos",
          title: "Some stuff that needs doing",
          active: false,
        },
        {
          icon: "email",
          text: "Contact",
          title: "Our Contact info",
          active: false,
        },
      ],
      items: [
        { title: "Click Me" },
        { title: "Click Me" },
        { title: "Click Me" },
        { title: "Click Me 2" },
      ],
    };
  },
};
</script>
  
  <style>
</style>