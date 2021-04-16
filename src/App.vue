<template>
  <img alt="Vue logo" src="./assets/logo.png">

  <Child :number="7">
    <template #default="{msg, hello}">
      <!-- You can bind data objects from Child and destructure in parent -->
      <h2>{{ msg }}</h2>

      <!-- You can use methods from parent -->
      <button @click="pressed">Press me</button> |
      <!-- or from the child itself -->
      <button @click="hello">Child Component Button</button>
      <br>
    </template>
    
    <template #multiply="{double, square}">
      <br>
      <!-- A named scope combined with props from child😎 -->
      <div>
        From Named Scope: {{ double }} | {{ square }}
      </div>
      <!-- You could also go about your normal html👇 -->
      Hello from named slot scope
    </template>
  </Child>
</template>

<script>
import Child from './components/Child.vue'

export default {
  name: 'App',
  components: {
    Child
  },
  methods: {
    pressed() {
      return alert('This is from parent')
    },
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
