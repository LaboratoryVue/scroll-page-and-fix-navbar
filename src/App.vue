<template>
  <v-app id="test">

    <v-container fluid id="scroll-target">

      <v-layout row>
        <v-toolbar :class="{ fixedNavigation: navFixed }">
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-toolbar-title>Scroll</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
              <v-btn flat>Link One</v-btn>
              <v-btn flat>Link Two</v-btn>
              <v-btn flat>Link Three</v-btn>
            </v-toolbar-items>
          </v-toolbar>
      </v-layout>

      <section id="scroll">
        <Block v-for="i in counter" :key="i" />
      </section>

    </v-container>

    <v-footer :fixed="footerFixed" app>
      <span>&copy; 2017</span>
    </v-footer>

  </v-app>
</template>

<script>
  import Block from './components/Block.vue'
  export default {
    name: 'App',
    data () {
      return {
        counter: 10,
        footerFixed: false,
        navFixed: false
      }
    },
    components: {
      Block
    },
    methods: {
      handleScroll (event) {
        this.navFixed = window.pageYOffset > 10
        console.log(window.pageYOffset)
      }
    },
    created () {
      window.addEventListener('scroll', this.handleScroll)
    },
    destroyed () {
      window.removeEventListener('scroll', this.handleScroll)
    }
  }
</script>

<style lang="scss" scoped>

  .toolbar {
    box-shadow: none;
    background-color: transparent;
  }

  .fixedNavigation {
    background-color: green;
    position: fixed;
    width: 80%;
    top: 0;
    left: 10%;
    box-shadow: 0px 2px 4px -1px rgba(0,0,0,0.2), 0px 4px 5px 0px rgba(0,0,0,0.14), 0px 1px 10px 0px rgba(0,0,0,0.12);
  }
</style>
