<template>
  <div id="app">
    <h1>Test Beacon Javascript</h1>
    <p>Send a beacon post to an API URL</p>
  </div>
</template>

<script>

export default {
  name: 'App',
  mounted() {
    document.addEventListener('visibilitychange', function() {
      if (document.hidden) {
        const sessionData = { foo: "bar" }

        navigator.sendBeacon('/api/v1/beacon', sessionData);
    }
  });
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  min-height: 100vh;
}

#app {
  position: absolute;
  top: 0; left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-flow: column nowrap;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
  background-color: #7bed9f;
}
</style>
