<script>
  import { Swipe, SwipeItem } from 'svelte-swipe'

  const swipeConfig = {
    autoplay: false,
    delay: 2000,
    showIndicators: true,
    transitionDuration: 1000,
    defaultIndex: 0,
  }

  const changeSlide = () => {
    console.log('changeSlide')
  }
  let swipe_holder_height = 0
  function heightChanged({ detail }) {
    swipe_holder_height = detail.height
  }
</script>

<h1>HIMARS</h1>
<div class="swiper_container" style="height:{swipe_holder_height}px">
  <Swipe {...swipeConfig} on:change={changeSlide}>
    <SwipeItem on:swipe_item_height_change={heightChanged}>
      <img src="https://via.placeholder.com/1200x600" alt="" />
    </SwipeItem>
    <SwipeItem on:swipe_item_height_change={heightChanged}>
      <img src="https://via.placeholder.com/1200x600" alt="" />
    </SwipeItem>
    <SwipeItem on:swipe_item_height_change={heightChanged}>
      <img src="https://via.placeholder.com/1200x600" alt="" />
    </SwipeItem>
    <SwipeItem on:swipe_item_height_change={heightChanged}>
      <img src="https://via.placeholder.com/1200x600" alt="" />
    </SwipeItem>
  </Swipe>
</div>

<style>
  .swiper_container {
    width: 100%;
  }
  .swiper_container img {
    width: 100%;
  }
</style>
