<template>
  <div id="app">
    <Main/>
  </div>
</template>

<script>
import 'bulma/css/bulma.css'
import Main from './components/Main'

export default {
  name: 'App',
  components: {
    Main
  }
}
</script>


<style lang="sass-loader">
$section-padding: 1rem;
@import '~bulma/bulma';
html{
background-color:#223334;
}
</style>
