<template>
  <div id="app">
    <overheader id="overheader"/>
    <header id="hear" />
    <wrap id="wrap" />
    <qfooter id="qfooter" />
  </div>
</template>

<script>
import overheader from './components/overheader.vue'
import hear from './components/hear.vue'
import wrap from './components/wrap.vue'
import qfooter from './components/qfooter.vue'

export default {
  name: 'app',
  components: {
    overheader,
    hear,
    wrap,
    qfooter
  }
}
</script>

<style src="./style.css" />
