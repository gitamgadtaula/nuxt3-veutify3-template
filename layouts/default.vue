<template>
  <v-app>
    <v-app-bar>
      <v-app-bar-title> SOE </v-app-bar-title>
      <v-spacer></v-spacer>

      <v-menu v-for="(item, index) in nav" open-on-hover :key="index">
        <template v-slot:activator="{ props }">
          <v-btn flat v-bind="props">
            <!-- <v-icon left dark>{{ item.icon }}</v-icon> -->
            {{ item.title }}
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="(link, i) in item.items" :key="'tab_' + i">
            <v-list-item-title>{{ link.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
      <v-spacer></v-spacer>
      <v-btn icon color="green">
        <v-icon color="green">mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>
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
      nav: [
        {
          icon: "home",
          text: "Home",
          title: "Home page",
          active: true,
          items: [
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me 2" },
          ],
        },
        {
          icon: "info",
          text: "About",
          title: "About this demo",
          active: false,
          items: [
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me 2" },
          ],
        },
        {
          icon: "assignment_turned_in",
          text: "Todos",
          title: "Some stuff",
          active: false,
          items: [
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me 2" },
          ],
        },
        {
          icon: "email",
          text: "Contact",
          title: "Our Contact",
          active: false,
          items: [
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me" },
            { title: "Click Me 2" },
          ],
        },
      ],
      links: ["Soe.com", "About Us", "Team", "Services", "Blog", "Contact Us"],
    };
  },
};
</script>
  
  <style>
</style>