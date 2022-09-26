<script>
  import { Swiper } from 'swiper/svelte';
  import { channels } from '~/assets/content.json';
  import ChannelItem from '~/modules/home/components/channel-item/channel-item.svelte';

  const breakpoints = {
    1024: {
      spaceBetween: 20,
      slidesPerView: 6,
      slidesPerGroup: 6,
    },
  };
</script>

<section>
  <h4 class="u-margin-bottom--md">Canais</h4>
  <Swiper class="c-swiper e-channel-slider" slidesPerView={3} slidesPerGroup={3} spaceBetween={16} {breakpoints}>
    {#each channels as channel}
      <ChannelItem {channel} />
    {/each}
  </Swiper>
</section>

<style lang="scss">
  .c-swiper {
    .swiper-slide {
      height: unset;
    }
  }
</style>
