<template>
  <Header />
  <router-view></router-view>
  <footer>Copyright &copy; 2021</footer>
</template>

<script>
import Header from './components/Header'

export default {
  
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: auto;
  max-width: 480px;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;

}

footer {
  border-top: #2c3e50 1px solid;
  padding: 1.2rem;
  color: #2c3e50;
  margin: 2rem 0;
}

</style>
