<template>
  <h1 :class="theme">Soy un reloj, mi hora es: {{ time }}</h1>
</template>

<script>
import dayjs from "dayjs";

const THEMES_VALUES = ["black", "red", "blue", "rainbow"];

export default {
  name: "Clock",
  props: {
    theme: {
      type: String,
      default: "black",
      validator: v => THEMES_VALUES.includes(v)
    }
  },
  data() {
    return {
      time: null
    }
  },
  mounted() {
    setInterval(() => this.getTime(), 1000);
  },
  methods: {
    getTime() {
      const date = dayjs();
      const hour = this.pad(date.hour());
      const minute = this.pad(date.minute());
      const second = this.pad(date.second());
      this.time = `${hour}:${minute}:${second}`;
    },
    pad(value) {
      return value.toString().padStart(2, "0");
    }
  }
}
</script>

<style>
.red {
  --font-color: red;
}

.blue {
  --font-color: blue;
}

.rainbow {
  --font-color: rebeccapurple;
}

h1 {
  color: var(--font-color);
}
</style>
