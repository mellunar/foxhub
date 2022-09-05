<script>
  // @ts-ignore
  import content from '~/assets/content.json';
  import HeaderSlider from '../modules/home/components/header-slider/header-slider.svelte';

  const headerItems = content.headerSlider;
</script>

<HeaderSlider items={headerItems} />
<div>
  <button class="c-button c-button--gradient">Teste</button>
  <button class="c-button c-button--general">Teste</button>
  <button class="c-button c-button--grad-hover">Teste</button>
</div>

<style>
  div {
    padding-top: 100px;
  }
</style>
