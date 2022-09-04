<script>
  import { Router } from '@roxi/routify';
  import { routes } from '../.routify/routes';
  import 'bootstrap-icons/font/bootstrap-icons.css';
  import './global.scss';
  import Footer from './core/components/footer/footer.svelte';
  import Navbar from './core/components/navbar/navbar.svelte';
</script>

<Router {routes} />
<Navbar />
<Footer />
