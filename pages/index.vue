<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">New Testament Redaction Calculator</h1>
      <div class="links">
        <a
          href="https://github.com/NathOrmond/nt-redaction/projects/1"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Project Tasks
        </a>
        <a
          href="https://github.com/NathOrmond/nt-redaction"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({})
</script>

<style>
.container {
  margin: 150px auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
  padding-bottom: 25px;
  margin: 10px;
}

.paragraph {
  text-align: left;
  margin: 5px;
  margin-left: 40px;
  margin-right: 40px;
  padding: 10px;
}
</style>
