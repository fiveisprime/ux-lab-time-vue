<template>
  <div id="app">
    <header className="App-header">
      <h1>Clock</h1>
    </header>
    <pre><code>{{time}}</code></pre>
    <button v-on:click="getTime()">Get New Time</button>
  </div>
</template>

<script>

export default {
  name: 'App',
  data: () => {
    return { internalTime: 'no time set' }
  },
  computed: {
    time() {
      return this.internalTime;
    }
  },
  methods: {
    async getTime() {
      const res = await fetch('');
      return this.internalTime = await res.text();
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
