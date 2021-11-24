<template>
  <h1 :class="theme">Soy un reloj, mi hora es: {{ time }}</h1>
</template>

<script>
import dayjs from "dayjs";

export default {
  name: "Clock",
  props: {
    theme: {
      type: String,
      default: "black",
      validator: v => {
        return v == "black" || v == "red" || v == "blue" || v == "rainbow" ? true : false;
      }
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
.black {
  color: green;
}

.red {
  color: red;
}

.blue {
  color: blue;
}

.rainbow {
  color: rebeccapurple;
}
</style>
