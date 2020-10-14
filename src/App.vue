<template>
  <div id="app">
    <TdForm />
  </div>
</template>

<script>
import TdForm from './components/TdForm'

export default {
  name: 'App',
  components: {
    TdForm,
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
#app{
  width: 100%;
  height: 100vh;
  background-color: black;
}
ul{
  margin-top: 10px;
}
h1{
  margin: 10px 0;
}


</style>
