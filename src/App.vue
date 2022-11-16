<template>
  <Search/>
  <SearchView/>
  <SearchFooter/>
</template>

<script scoped>
import Search from './components/Search.vue'
import SearchView from './components/SearchView.vue'
import SearchFooter from './components/SearchFooter.vue'
import HomeNav from './components/HomeNav.vue'

export default {
  name: 'App',
  components: {
    Search,
    SearchView,
    SearchFooter,
    HomeNav
  },
}

</script>
