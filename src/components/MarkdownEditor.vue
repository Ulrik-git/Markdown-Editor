<template>
  <div class="markdown-editor">
    <textarea
      v-model="markdown"
      placeholder="Enter your markdown here..."
      ref="markdownTextarea"
    ></textarea>
    <div v-html="compiledMarkdown" class="preview"></div>
  </div>
</template>

<script>
import { marked } from 'marked';

export default {
  data() {
    return {
      markdown: '',
      placeholderText: 'Your Markdown preview will appear here...',
      storageKey: 'markdown-content', // Key used to store data in local storage
    };
  },
  computed: {
    compiledMarkdown() {
      if (this.markdown.trim() === '') {
        // If markdown is empty, return placeholder text with basic formatting
        return `<p style="color: #aaa;">${this.placeholderText}</p>`;
      }
      return marked(this.markdown, { breaks: true });
    },
  },
  watch: {
    markdown(newContent) {
      // Save the new content to local storage whenever it changes
      localStorage.setItem(this.storageKey, newContent);
    },
  },
  mounted() {
    // Load saved content from local storage if available
    const savedContent = localStorage.getItem(this.storageKey);
    if (savedContent) {
      this.markdown = savedContent;
    }
    this.$refs.markdownTextarea.focus(); // Focus the textarea on page load
  },
};
</script>

<style scoped>
html, body {
  margin: 0;
  padding: 0;
  height: 100%;
  font-family: Arial, sans-serif;
}

.markdown-editor {
  display: flex;
  height: 100vh;
}

textarea {
  resize: none;
  padding-top: 15px;
}

.preview {
  border-top: 1px solid #ddd;
  margin-top: 1px;
  background: #f9f9f9;
  overflow-y: auto;
  white-space: pre-wrap; /* Ensure that newlines in markdown are preserved */
}

textarea, .preview {
    width: 50%;
    height: 50%;
    box-sizing: border-box;
    font-family: monospace;
    font-size: 16px;
    text-align: center;
    height: 80%;
    border: 2px solid black;
}
</style>
