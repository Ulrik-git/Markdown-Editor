<template>
  <div id="app">
    <MarkdownEditor />
  </div>
</template>

<script>
import MarkdownEditor from './components/MarkdownEditor.vue';

export default {
  components: {
    MarkdownEditor,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  margin-top: 40px;
}
</style>
