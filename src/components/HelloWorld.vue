<template>
  <div class="hello">
    <h2>A Daily de hoje será na ordem</h2>
    <h1>{{ dailyOrder }}</h1>
    <br>
    <h4>{{ msg }}</h4>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data: () => ({
    msg: "Hello Vue!",
    now: new Date()
  }),
  computed: {
    currentYear: () => {
      return this.now.getFullYear()
    },
    currentYearDays: function() {
      const startDate = new Date(this.now.getFullYear(), 0, 0)
      return Math.ceil((this.now - startDate) / (1000 * 60 * 60 * 24))
    },
    isPairDay: function() {
      return this.currentYearDays % 2 === 0
    },
    dailyOrder: function() {
      return this.isPairDay ? "ALFABETICA" : "ALFABETICA INVERSA"
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
