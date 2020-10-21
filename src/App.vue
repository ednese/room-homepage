<template>
  <div id="app">
    <Header/>
    <Top/>
    <Footer/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Header from './components/Header/Header'
import Top from './components/Top/Top'
import Footer from './components/Footer/Footer'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Header,
    Top,
    Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Spartan:wght@500;600;700&display=swap');
* {
  margin: 0;
  padding: 0;
}
#app {
  font-family: Spartan, 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

li {
  list-style: none;
}

a {
  text-decoration: none;
}
</style>
