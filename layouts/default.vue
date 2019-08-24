<template lang='pug'>
v-app
  v-navigation-drawer(app v-model='drawer')
  v-app-bar(app collapse-on-scroll)
    v-app-bar-nav-icon(@click='drawer = !drawer')
    v-toolbar-title Le Titre
    v-spacer
    dark
  v-content
    nuxt
</template>

<script lang='coffee'>
import dark from '~/components/dark'

export default
  components: {dark}

  data: ->
    drawer: null
</script>