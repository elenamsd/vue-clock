<template>
  <h1>Soy un reloj, mi hora es: {{ time }}</h1>
</template>


<script>
import dayjs from "dayjs";
export default {
  name: "Clock",
  data() {
    return {
      date: this.getDate(),
      time: this.getTime()
    }

  },
  methods: {
    getDate() {
      return new Date()
    },
    getTime(){
      const date = dayjs();
      const hour= date.hour().toString().padStart(2,'0');
      const minute= date.minute().toString().padStart(2,'0');
      const second = date.second().toString().padStart(2,'0');
      return `${hour}:${minute}:${second}`;
    }
  }
}
</script>
