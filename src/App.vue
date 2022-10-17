<template>
  <Search/>
  <SearchView/>
  <SearchFooter/>
</template>

<script>
import Search from './components/Search.vue'
import SearchView from './components/SearchView.vue'
import SearchFooter from './components/SearchFooter.vue'

export default {
  name: 'App',
  components: {
    Search,
    SearchView,
    SearchFooter,
  }
}
</script>
