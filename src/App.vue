<template>
  <div id="app">
    <TodoList />
  </div>
</template>

<script>
import TodoList from './components/TodoList';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    TodoList,
  },
  mounted: function () {
    axios
      .get('https://kaamelott.chaudie.re/api/random/personnage/arthur', {
        withCredentials: true,
      })
      .then(response => {
        console.log(response)
      })
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
  display: flex;
  flex-direction: column-reverse;
  width: 90%;
  margin-top: 10px;
  font-size: 1.5rem;

}
h1{
  margin: 10px 0;
  color: antiquewhite ;
}
</style>
