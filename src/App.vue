<template lang="">

<AppHeader />
<AppMain />

</template>
<script>
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue';
export default {
  name : 'App',
  components : {
    AppHeader,
    AppMain,
  },
  created() {
    
  },
}
</script>
<style lang="scss">
@import './styles/general.scss';
@import "bootstrap/scss/bootstrap";

</style>