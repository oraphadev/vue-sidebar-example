<template>
  <div id="app">
    <Sidebar />
  </div>
</template>

<script>
import Sidebar from '@/components/Sidebar'

export default {
  name: 'App',
  components: {
    Sidebar
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  font-family: 'Outfit';
}

body, html {
  margin: 0;
  padding: 0;
  background: #17181a;
}

span {
  font-family: 'Material Symbols Outlined';
  font-weight: normal;
  font-style: normal;
  font-size: 24px;
  line-height: 1;
  letter-spacing: normal;
  text-transform: none;
  display: inline-block;
  white-space: nowrap;
  word-wrap: normal;
  direction: ltr;
  font-feature-settings: 'liga';
  -webkit-font-feature-settings: 'liga';
  -webkit-font-smoothing: antialiased;
}
</style>

<style scoped>
#app {
  width: 100%;
  height: 100vh;
}
</style>
