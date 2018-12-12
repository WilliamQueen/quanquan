<template>
  <div id="app">
			<site></site>
			<index></index>
  </div>
</template>

<script>
	import Site from './components/Header'
	import Index from './pages/index'
export default {
  name: 'App',
  data(){
  	return {
  		
  	}
  },
  components: {
  	Site,
  	Index
  }
}
</script>

<style lang="scss">
	
</style>
