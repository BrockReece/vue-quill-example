<template>
  <div id="app">
    <quill v-model="content" output="html" :config="{theme: 'bubble'}" :bus="bus">
        <p>
            This is issue, I need
            <strong>best</strong>
            grammar
        </p>
    </quill>
    {{ content }}
  </div>
</template>

<script>
import Hello from './components/Hello';

export default {
  name: 'app',
  components: {
    Hello,
  },

  data() {
    return {
      content: '<p>This is issue, I need best grammar.</p><p><br></p><p>Tell me about some supercroud. </p>',
      bus,
    };
  },

  mounted() {
    bus.$emit('focus-editor');
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
