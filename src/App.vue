<template>  
<section>
    <NavBar ></Navbar>
      <router-view ></router-view>
    <FooterBar ></FooterBar>
  </section>
</template>
<script>
import NavBar from '@/components/NavBar.vue'
import FooterBar from './components/FooterBar.vue';

export default {
  name: 'App',
  components: {
    NavBar,
    FooterBar
}
}
</script>
<style>

*{
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
::-webkit-scrollbar {
        width: 6px;
        border-left: 1px solid #E6ECF8;
    }
    ::-webkit-scrollbar-thumb {
        background-color: var(--dark-navy);
        cursor: grab;
    }
    *{
      font-family: Helvetica;
      padding: 0;
      margin: 0;
      box-sizing: border-box;
    }
    h1{
      text-align: center;
      font-size: 42px;
      margin-bottom: 30px;
      color: #222;
    }
    .main-container{
      margin: 50px;
      min-height: 250px;
    }
</style>
