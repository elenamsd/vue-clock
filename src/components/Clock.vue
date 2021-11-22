<template>
  <h1>Soy un reloj, mi hora es: {{ date }}</h1>
</template>


<script>
export default {
  name: "Clock",
  data() {
    return {
      date: this.getDate()
    }

  },
  methods: {
    getDate() {
      return new Date();
    }
  }
}
</script>
