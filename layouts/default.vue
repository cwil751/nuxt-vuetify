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

    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
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
          icon: 'mdi-chart-bubble',
          title: 'About',
          to: '/about'
        },
        {
          icon: 'mdi-file-document-multiple',
          title: 'Resume',
          to: '/resume'
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
