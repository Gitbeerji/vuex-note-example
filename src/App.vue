<template>
  <div id="app">
    <Notes></Notes>
  </div>
</template>

<script>
import Notes from './components/Notes'
import 'semantic-ui-css/semantic.min.css'

export default {
  name: 'App',
  components: {
    Notes
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.notes {
  margin-top: 32px;
}

.notes .ui textarea {
  font-size: 16px;
  margin: 16px 0;
}

.ui.items > .item > .content .header {
  display: block;
  cursor: pointer;
}

.ui.items > .item > .meta {
  width: 88px;
  color: rgba(0,0,0,0.4);
  margin-top: 0;
  margin-bottom: 16px;
}

.icon.trash.alternate {
  cursor: pointer;
}
</style>
