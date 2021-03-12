<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      fixed
      app
      :permanent="$vuetify.breakpoint.mdAndUp"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
      <v-container>
        <div class="rtl d-md-none">
          <v-btn fab small fixed top dark >
            <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
         </v-btn>
        </div>
      </v-container>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
      
      <v-speed-dial
        v-model="dialShare"
        absolute
        right
        bottom
        direction="left"
        open-on-hover
      >
        <template v-slot:activator>
          <v-btn fab bottom small color="primary">
            <v-icon v-if="dialShare">mdi-close</v-icon>
            <v-icon v-else>mdi-share-variant</v-icon>
          </v-btn>
        </template>
        <v-btn
          dark
          fab
          bottom
          color="green"
          small
          :href="'https://github.com/cwil751'"
          target="_blank"
        >
          <v-icon>mdi-github</v-icon>
        </v-btn>
        <v-btn
          dark
          fab
          bottom
          color="green"
          small
          :href="'https://twitter.com/cwil751'"
          target="_blank"
        >
          <v-icon>mdi-twitter</v-icon>
        </v-btn>
        <v-btn
          dark
          fab
          bottom
          color="green"
          small
          :href="'https://www.linkedin.com/in/cory-wilson-a9a571150/'"
          target="_blank"
        >
          <v-icon>mdi-linkedin</v-icon>
        </v-btn>
      </v-speed-dial>
      
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-account-circle',
          title: 'About',
          to: '/about'
        },
        {
          icon: 'mdi-file-document-multiple',
          title: 'Resume',
          to: 'resume'
        }
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'cw.'
    }
  }
}
</script>
