<template>
  <v-app>
    <v-app-bar
      app
    >
      <h1>Socialfy</h1>
      <v-spacer />
      <v-btn
        class="justify-end"
        color="primary"
        plain
      >
        Log In
      </v-btn>
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      app
    >
      <span>&copy; MJP {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data () {
    return {
    }
  }
}
</script>
