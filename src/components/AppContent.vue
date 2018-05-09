<template>
  <div id="app-content">
    {{ content }}
  </div>
</template>
<script>
  export default {
    name: 'app-content',
    data() {
      return {
        content: 'this is main content region'
      }
    }
  }
</script>
