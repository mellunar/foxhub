<script>
  export let item;
</script>

<article class="e-header-slide">
  <div class="e-header-slide__text">
    <h2>{item.title}</h2>
    <p class="u-margin-top--sm u-hide--mobile">{item.description}</p>
    <div class="u-display--flex u-flex-align--center e-header-slide__text-buttons">
      <a class="c-button c-button--grad-hover u-font-size--md e-header-slide__text-button" href="javascript://">
        Assistir
      </a>
      <button class="u-margin-left--md e-header-slide__text-favorite e-header-slide__text-button u-hide--mobile">
        <i class="bi bi-plus" /> Favoritos
      </button>
    </div>
    <a href="javascript://" class="u-link--cover" />
  </div>
  <div class="e-header-slide__image">
    <img class="u-hide--desktop" alt={item.title} src={item.mobile} />
    <img class="u-hide--mobile" alt={item.title} src={item.desktop} />
    <a href="javascript://" class="u-link--cover" />
  </div>
</article>

<style src="./header-slider-item.scss"></style>
