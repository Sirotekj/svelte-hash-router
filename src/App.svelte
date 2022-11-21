<script>

  import { routes, Router } from 'svelte-hash-router'
  import Home from './routes/Home.svelte'
  import Himars from './routes/Himars.svelte'
  import Javelin from './routes/Javelin.svelte'
  import Bayraktar from './routes/Bayraktar.svelte'
  import M777 from './routes/M777.svelte'

  routes.set({
    '/': Home,
    '/himars': Himars,
    '/javelin': Javelin,
    '/bayraktar': Bayraktar,
    '/m777': M777,
  })
</script>

<h1>Main Page</h1>
<nav>
  <a href="#/">Home</a>
  <a href="#/himars">Himars</a>
  <a href="#/javelin">Javelin</a>
  <a href="#/bayraktar">Bayraktar</a>
  <a href="#/m777">M777</a>
</nav>
<Router/>

<style>

</style>
