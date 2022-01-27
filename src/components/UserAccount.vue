<template>
<div>  <h1>Добрый день, [Username]!</h1>
  <requests-tracker :requests="requests"/></div>

</template>

<script>
import RequestsTracker from './RequestsTracker.vue'
export default {
  name: 'UserAccount',
  components: {
    RequestsTracker
  },
  props:{
      requests: Array,
  },
}
</script>

<style>

</style>