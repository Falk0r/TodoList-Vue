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
@import url('https://fonts.googleapis.com/css2?family=Permanent+Marker&display=swap');

*{
  margin: 0;
  padding: 0;
  font-family: 'Permanent Marker', cursive;
}
body{
  display: flex;
  justify-content: center;
  background-color: black;
}

#app{
  width: 100%;
  max-width: 700px;
  min-height: 100vh;
  background-color: black;
}
ul{
  margin-top: 10px;
  font-family: 'Permanent Marker', cursive;
}
h1{
  margin: 10px 0;
  font-family: 'Permanent Marker', cursive;
}


</style>
