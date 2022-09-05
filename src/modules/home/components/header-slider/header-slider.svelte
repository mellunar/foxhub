<script>
  import { Autoplay, Navigation, Pagination } from 'swiper';
  import { Swiper, SwiperSlide } from 'swiper/svelte';
  import HeaderSliderItem from '../header-slider-item/header-slider-item.svelte';

  export let items;

  const pagination = { clickable: true, hideOnClick: false };
  const autoplay = { delay: 10000 };
</script>

<section class="e-header-slider">
  <Swiper class="c-swiper" modules={[Autoplay, Navigation, Pagination]} loop navigation {pagination} {autoplay}>
    {#each items as item}
      <SwiperSlide><HeaderSliderItem {item} /></SwiperSlide>
    {/each}
  </Swiper>
</section>

<style src="./header-slider.scss"></style>
