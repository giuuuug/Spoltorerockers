<script>
  import { onMount, tick } from 'svelte';

  onMount(async () => {
    await tick(); // Attende che Svelte aggiorni il DOM
    // @ts-ignore
    if (window.GoFundMe && typeof window.GoFundMe.init === 'function') {
      // @ts-ignore
      window.GoFundMe.init();
    }
  });
</script>

<div class="gfm-embed"
  data-url="https://www.gofundme.com/f/rinascita-verticale-sentieri-e-area-boulder-a-pescosansones/widget/large?sharesheet=fundraiser%20sidebar&attribution_id=sl:131798c4-de2c-4c02-bca6-ca029382c933">
</div>
