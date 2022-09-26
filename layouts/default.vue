<template>
  <v-app>
    <v-toolbar app>
      <span class="hidden-sm-and-up">
        <v-toolbar-side-icon @click="sidebar = !sidebar"> </v-toolbar-side-icon>
      </span>
      <v-toolbar-title>
        <router-link to="/" tag="span" style="cursor: pointer">
          Hello
        </router-link>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      Logout
      <!-- <v-toolbar-items class="hidden-xs-only">
        <v-btn flat v-for="item in menuItems" :key="item.title" :to="item.path">
          <v-icon left dark>{{ item.icon }}</v-icon>
          {{ item.title }}
        </v-btn>
      </v-toolbar-items> -->
    </v-toolbar>

    <v-content>
      <slot />
    </v-content>
  </v-app>
</template>
  
  <script>
export default {};
</script>
  
  <style>
</style>