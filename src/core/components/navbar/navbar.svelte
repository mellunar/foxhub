<script>
  import { clickOutside } from '~/core/directives/click_outside';

  let menuOpened = false;
  let userActions = false;

  let actionsButtonRef;
  let userActionsRef;

  function toggleMenu() {
    menuOpened = !menuOpened;
  }

  function toggleUserActions(event) {
    userActions = !userActions;

    if (event) {
      event.stopPropagation();
    }

    if (userActions) {
      window.addEventListener('click', closeClickOutside);
    } else {
      window.removeEventListener('click', closeClickOutside);
    }
  }

  function closeClickOutside(event) {
    if (actionsButtonRef.contains(event.target)) {
      return;
    }

    if (!userActionsRef.contains(event.target)) {
      toggleUserActions();
    }
  }
</script>

<header class="e-navbar">
  <nav class="e-navbar__container">
    <button
      class="e-navbar__button e-navbar__button-menu u-hide--desktop"
      use:clickOutside
      on:clickoutside={toggleMenu}
      on:click={toggleMenu}>
      {#if menuOpened}
        <i class="bi bi-x" />
      {:else}
        <i class="bi bi-list" />
      {/if}
    </button>

    <a class="e-navbar__logo" href="/">
      <img src="images/foxhub2.png" alt="logo" />
    </a>

    <div class="u-display--flex e-navbar__list" class:e-navbar__list-opened={menuOpened}>
      <a class="e-navbar__item u-hide--desktop" href="javascript:void()">Pesquisar</a>
      <a class="e-navbar__item" href="javascript:void()">Canais</a>
      <a class="e-navbar__item" href="javascript:void()">Programas</a>
      <a class="e-navbar__item" href="javascript:void()">Séries</a>
      <a class="e-navbar__item" href="javascript:void()">Filmes</a>
      <a class="e-navbar__item" href="javascript:void()">Favoritos</a>
    </div>

    <div class="e-navbar__actions">
      <button class="e-navbar__button u-hide--mobile"><i class="bi bi-search" /></button>
      <button
        class="e-navbar__button e-navbar__actions-user"
        bind:this={actionsButtonRef}
        on:click={toggleUserActions}>
        <i class="e-navbar__user-icon u-margin-right--sm bi bi-person-circle" />
        {#if userActions}
          <i class="bi bi-chevron-up u-hide--mobile" />
        {:else}
          <i class="bi bi-chevron-down u-hide--mobile" />
        {/if}
      </button>

      <div
        class="e-navbar__actions-menu"
        bind:this={userActionsRef}
        class:e-navbar__actions-menu-opened={userActions}
        class:e-navbar__actions-menu-shadow={userActionsRef?.scrollHeight > 0}>
        <div class="u-padding-x--xl u-padding-y--md">
          <button class="c-button c-button--general u-width--100 u-display--table">Entrar</button>
          <button class="c-button c-button--general u-width--100 u-display--table u-margin-top--md">
            Entrar com Operadora
          </button>
          <p class="u-margin-top--md u-text-align--center u-user-select--none">Ainda não é assinante?</p>
          <button class="c-button c-button--gradient u-width--100 u-display--table u-margin-top--md">
            Seja assinante
          </button>
        </div>
      </div>
    </div>
  </nav>
</header>

<style lang="scss">
  @import 'navbar.scss';
</style>
