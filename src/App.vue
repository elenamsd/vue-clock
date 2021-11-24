<template>
  <h1>Hola</h1>
  <Clock></Clock>
  <Clock theme="red"></Clock>
  <Clock theme="blue"></Clock>
  <Clock theme="rainbow"></Clock>
</template>


<script>
import Clock from "./components/Clock.vue"
export default {
  name: "App",
  components: {
    Clock
  }
}
</script>
