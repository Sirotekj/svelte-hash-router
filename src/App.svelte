<script>
  import Router from 'svelte-spa-router'

  import { Swiper, SwiperSlide } from 'swiper/svelte';
  import { Navigation } from 'swiper'
  import 'swiper/css';

  import Home from './routes/Home.svelte'
  import Himars from './routes/Himars.svelte'
  import Javelin from './routes/Javelin.svelte'
  import Bayraktar from './routes/Bayraktar.svelte'
  import M777 from './routes/M777.svelte'

  const routes = {
    '/': Home,
    '/himars': Himars,
    '/javelin': Javelin,
    '/bayraktar': Bayraktar,
    '/m777': M777,
  }

  const items=[
    "himars",
    "javelin",
    "bayraktar",
    "m777"
  ]

  let initialId = 1;
  const scrollToTop = () => {console.log("scrollToTop")}
  const changeSlide = (e) => {
    console.log("changeSlide", e.detail[0].activeIndex)
    window.location = "#/"+items[e.detail[0].activeIndex];
  }

</script>

<h1>Main Page</h1>
<div class="swiper_container">
  <Swiper
    draggable
    navigation
    autoHeight={true}
    modules={[Navigation]}
    spaceBetween={20}
    key={initialId}
    initialSlide={initialId - 1}
    on:slideChangeTransitionStart={scrollToTop}
    on:slideChangeTransitionEnd={changeSlide}
    >
      <SwiperSlide>
        <img src="https://via.placeholder.com/1200x600" alt="" />
      </SwiperSlide>
      <SwiperSlide>
        <img src="https://via.placeholder.com/1200x600" alt="" />
      </SwiperSlide>
      <SwiperSlide>
        <img src="https://via.placeholder.com/1200x600" alt="" />
      </SwiperSlide>
      <SwiperSlide>
        <img src="https://via.placeholder.com/1200x600" alt="" />
      </SwiperSlide>
  </Swiper>
</div>

<nav>
  <a href="#/">Home</a>
  <a href="#/himars">Himars</a>
  <a href="#/javelin">Javelin</a>
  <a href="#/bayraktar">Bayraktar</a>
  <a href="#/m777">M777</a>
</nav>
<Router {routes} />

<style>
  .swiper_container {
    width: 100%;
  }
  .swiper_container img {
    width: 100%;
  }
</style>
