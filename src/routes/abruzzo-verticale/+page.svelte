<script>
  import { onMount } from "svelte";
  import { base } from '$app/paths';

  let fadeIn = false;

  onMount(() => {
    setTimeout(() => {
      fadeIn = true;
    }, 100);
  });
</script>

<div class="hero {fadeIn ? 'fade-in' : ''}">
  <div class="hero-content">
    <h1>Abruzzo Verticale</h1>
    <p class="hero-subtitle">La nostra community dedicata alla montagna in Abruzzo</p>
  </div>
</div>

<section class="section">
  <div class="container">
    <div class="row">
      <div class="col-6">
        <h2 class="section-title">Il Progetto</h2>
        <p>
          Abruzzo Verticale è la vivace community WhatsApp ideata da
          Spoltorerockers per unire tutti gli appassionati della montagna
          abruzzese, con un focus particolare sull'arrampicata. Il nostro
          intento primario è tessere una solida rete di climbers che possano
          scambiarsi avventure verticali, pianificare entusiasmanti uscite in
          falesia e offrirsi supporto reciproco.
        </p>
        <p>
          La nostra community accoglie chiunque ami la montagna, dai neofiti
          dell'arrampicata agli scalatori più esperti. Ma Abruzzo Verticale è
          molto più di un semplice gruppo per climbers: è un punto di
          riferimento per tutti coloro che vivono e amano la montagna abruzzese
          a 360 gradi.
        </p>
        <p>
          Qui potrai trovare compagni per trekking ed escursioni alla scoperta
          delle vette, condividere la passione per l'alpinismo, trovare
          occasioni nel marketplace dedicato alla compravendita di attrezzatura
          e abbigliamento tecnico montano, rimanere aggiornato su progetti di
          valorizzazione del territorio ed essere informato sui numerosi eventi
          organizzati per vivere insieme la montagna abruzzese in tutte le sue
          sfaccettature.
        </p>
        <div class="cta-box">
          <h3>Unisciti alla Community</h3>
          <p>
            Clicca sul pulsante qui sotto per unirti al
            gruppo WhatsApp più grande d'Abruzzo.
          </p>
          <a href="https://chat.whatsapp.com/HwoIrojkiDKAUgEGKdpuqO" class="btn btn-primary">Unisciti</a>
        </div>
      </div>
      <div class="col-6">
        <img
          src="{base}/img/Abruzzo_verticale.jpg"
          alt="Abruzzo Verticale Community"
          class="img-fluid rounded"
        />
      </div>
    </div>
  </div>
</section>

<section class="section bg-light">
  <div class="container">
    <h2 class="section-title">Eventi e Incontri</h2>
    <div class="row">
      <div class="col-12">
        <div class="no-events-card">
          <div class="no-events-icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round">
              <rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect>
              <line x1="16" y1="2" x2="16" y2="6"></line>
              <line x1="8" y1="2" x2="8" y2="6"></line>
              <line x1="3" y1="10" x2="21" y2="10"></line>
            </svg>
          </div>
          <h3>Nessun evento in programma</h3>
          <p>
            Al momento non ci sono eventi programmati per la community Abruzzo Verticale.
            Torna a visitarci presto per scoprire le prossime attività ed incontri!
          </p>
          <p class="no-events-cta">
            Hai un'idea per un evento? Condividila con noi nella community WhatsApp!
          </p>
        </div>
      </div>
    </div>
  </div>
</section>

<style lang="scss">
  @use "sass:color";
  .hero {
    height: 70vh;
    background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), 
                url('/img/Gruppo_whatsapp.jpg') center/cover no-repeat;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: white;
    margin-bottom: 3rem;
    opacity: 0; 
    transition: opacity 0.8s ease;

    &.fade-in {
      opacity: 1;
    }
    
    .hero-content {
      max-width: 800px;
      padding: 0 2rem;
    }
    
    h1 {
      font-size: 3rem;
      margin-bottom: 1rem;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
    }
    
    .hero-subtitle {
      font-size: 1.5rem;
      text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
    }
  }

  .img-fluid {
    max-width: 100%;
    height: auto;
  }

  .rounded {
    border-radius: 8px;
  }

  .cta-box {
    background: linear-gradient(135deg, #4e4c4f, #232220);
    color: white;
    padding: 2rem;
    border-radius: 8px;
    margin-top: 2rem;

    h3 {
      margin-bottom: 1rem;
    }

    p {
      margin-bottom: 1.5rem;
      opacity: 0.9;
    }

    
  }

  .bg-light {
    background-color: #f8f9fa;
  }

  .no-events-card {
    background-color: white;
    border-radius: 8px;
    padding: 3rem 2rem;
    text-align: center;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
    margin: 1rem 0;
  }

  .no-events-icon {
    margin: 0 auto 1.5rem;
    width: 80px;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: linear-gradient(135deg, #27ae60, #2ecc71);
    border-radius: 50%;
    color: white;
  }

  .no-events-card h3 {
    font-size: 1.5rem;
    margin-bottom: 1rem;
    color: #333;
  }

  .no-events-card p {
    color: #666;
    font-size: 1.1rem;
    max-width: 600px;
    margin: 0 auto 1rem;
  }

  .no-events-cta {
    font-weight: 600;
    color: #27ae60;
    margin-top: 1.5rem;
  }
</style>
