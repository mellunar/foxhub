<script>
  import { headerSlider } from '~/assets/content.json';
  import ChannelSlider from '~/modules/home/components/channel-slider/channel-slider.svelte';
  import HeaderSlider from '~/modules/home/components/header-slider/header-slider.svelte';

  const pagination = { clickable: true, hideOnClick: false };
</script>

<HeaderSlider items={headerSlider} />

<div class="e-home-page">
  <ChannelSlider />
</div>

<div class="buttons">
  <button class="c-button c-button--gradient">Teste</button>
  <button class="c-button c-button--general">Teste</button>
  <button class="c-button c-button--grad-hover">Teste</button>
</div>

<style src="./home.scss"></style>
