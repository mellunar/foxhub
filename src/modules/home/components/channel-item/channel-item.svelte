<script>
  import { SwiperSlide } from 'swiper/svelte';

  export let channel;
</script>

<SwiperSlide class={`e-channel-item e-channel-item--${channel.id}`}>
  <img alt={channel.title} src={channel.logo} />
  <a href="javascript://" class="u-link--cover" />
</SwiperSlide>

<style src="./channel-item.scss"></style>
