<template>
  <v-app>
    <v-app-bar>
      <v-app-bar-nav-icon class="hidden-md-and-up" @click="toggleDrawer">
        <span class="material-icons"> menu </span>
      </v-app-bar-nav-icon>
      <v-app-bar-title> SOE </v-app-bar-title>
      <v-spacer></v-spacer>
      <div class="hidden-sm-and-down">
        <v-menu v-for="(item, index) in nav" open-on-hover :key="index">
          <template v-slot:activator="{ props }">
            <v-btn flat v-bind="props">
              {{ item.title }}
            </v-btn>
          </template>

          <v-list :items="item.items"></v-list>
        </v-menu>
      </div>
      <v-spacer></v-spacer>

      <v-btn icon>
        <span class="material-icons"> account_circle </span>
        <v-tooltip activator="parent" location="bottom"
          >johndoe@email.com</v-tooltip
        >
      </v-btn>
      <v-btn icon>
        <span class="material-icons"> logout </span>
        <v-tooltip activator="parent" location="bottom">Logout</v-tooltip>
      </v-btn>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" temporary>
      <v-menu v-for="(item, index) in nav" open-on-hover :key="index">
        <template v-slot:activator="{ props }">
          <v-btn flat v-bind="props">
            {{ item.title }}
          </v-btn>
        </template>

        <v-list :items="item.items"></v-list>
      </v-menu>
    </v-navigation-drawer>

    <v-main>
      <v-container fluid>
        <slot />
      </v-container>
    </v-main>

    <v-footer color="primary">
      <v-row no-gutters>
        <v-btn color="white" variant="text" class="mx-2" rounded="xl">
          soe.com
        </v-btn>
        <v-btn color="white" variant="text" class="mx-2" rounded="xl">
          Contact </v-btn
        ><v-btn color="white" variant="text" class="mx-2" rounded="xl">
          Twitter </v-btn
        ><v-btn color="white" variant="text" class="mx-2" rounded="xl">
          Facebook
        </v-btn>
        <v-spacer />
        <v-btn color="white" variant="text" class="mx-2" rounded="xl">
          Privacy Policy
        </v-btn>
        <v-btn color="white" variant="text" class="mx-2" rounded="xl">
          Terms of use
        </v-btn>
        <v-btn color="white" variant="text" class="mx-2" rounded="xl">
          &copy; 2022
        </v-btn>
      </v-row>
    </v-footer>
  </v-app>
</template>
  
<script>
export default {
  data() {
    return {
      drawer: false,
      nav: [
        {
          icon: "home",
          text: "Home",
          title: "Home page",
          active: true,
          items: [
            { title: "Click Me", value: "1" },
            { title: "Click Me", value: "2" },
            { title: "Click Me", value: "3" },
            { title: "Click Me 2", value: "4" },
          ],
        },
        {
          icon: "info",
          text: "About",
          title: "About this demo",
          active: false,
          items: [
            { title: "Click Me", value: "1" },
            { title: "Click Me", value: "2" },
            { title: "Click Me", value: "3" },
            { title: "Click Me 2", value: "4" },
          ],
        },
        {
          icon: "assignment_turned_in",
          text: "Todos",
          title: "Some stuff",
          active: false,
          items: [
            { title: "Click Me", value: "1" },
            { title: "Click Me", value: "2" },
            { title: "Click Me", value: "3" },
            { title: "Click Me 2", value: "4" },
          ],
        },
        {
          icon: "email",
          text: "Contact",
          title: "Our Contact",
          active: false,
          items: [
            { title: "Click Me", value: "1" },
            { title: "Click Me", value: "2" },
            { title: "Click Me", value: "3" },
            { title: "Click Me 2", value: "4" },
          ],
        },
      ],
      links: ["Soe.com", "About Us", "Team", "Services", "Blog", "Contact Us"],
    };
  },
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    },
  },
};
</script>
<script setup>
useHead({
  link: [
    {
      rel: "stylesheet",
      href: "https://fonts.googleapis.com/icon?family=Material+Icons",
    },
  ],
});
</script>
<style>
</style>