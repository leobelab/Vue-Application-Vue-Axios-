<template>
  <h1>{{ title }}</h1>
</template><!-- because there are different templates for different components
                and we see some of them and not others at different moment -->

<script>
export default {
  name: 'App',
  data() {
    return {
      title: 'My First Vu App :)'
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
