<script>
  import { onMount } from 'svelte';
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
    <h1>Benvenuti nel mondo verticale di Spoltorerockers</h1>
    <p class="hero-subtitle">Gruppo di arrampicata e avventura in Abruzzo</p>
  </div>
</div>

<section class="section">
  <div class="container">
    <h2 class="section-title">Chi Siamo</h2>
    <div class="row">
      <div class="col-6">
        <p>
          Spoltorerockers è un gruppo di appassionati di arrampicata nato nel 2025. 
          La nostra missione è promuovere l'arrampicata sportiva, valorizzare il territorio montano abruzzese 
          e creare una community di climbers unita dalla passione per la verticalità.
        </p>
        <p>
          Organizziamo uscite, eventi formativi, progetti di sviluppo delle falesie locali e 
          iniziative per avvicinare nuove persone a questo meraviglioso sport a contatto con la natura.
        </p>
      </div>
      <div class="col-6">
        <img src="{base}/img/Arrampicata.jpg" alt="Arrampicata in Abruzzo" class="img-fluid rounded" />
      </div>
    </div>
  </div>
</section>

<section class="section bg-light">
  <div class="container">
    <h2 class="section-title">Il Nostro Team</h2>
    <div class="row justify-center">
      <div class="col-4">
        <div class="card team-card">
          <div class="team-avatar">
            <img src="{base}/faces/giuug.jpeg" alt="Matteo Giuliani" class="avatar-image" />
          </div>
          <h3>Matteo Giuliani</h3>
          <p class="team-role">Fondatore & Sviluppatore</p>
          <p>Ingegnere Informatico con la passione per gli sport. Per rilassarmi scrivo codice o faccio un giro in montagna.</p>
          <div class="social-icons">
            <a href="https://www.instagram.com/giuuug_/" target="_blank" rel="noopener noreferrer" aria-label="Instagram">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path><line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line></svg>
            </a>
            <!-- <a href="https://tiktok.com/@tuouser" target="_blank" rel="noopener noreferrer" aria-label="TikTok">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 12a4 4 0 1 0 0 8 4 4 0 0 0 0-8z"></path><path d="M19.65 7.35A6 6 0 0 0 16 6h-3v10a3 3 0 1 1-3-3h1V9a6 6 0 0 0-6 6v.1"></path></svg>
            </a> -->
            <a href="https://github.com/giuuuug" target="_blank" rel="noopener noreferrer" aria-label="Github">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22"></path></svg>
            </a>
            <a href="https://www.linkedin.com/in/matteo-giuliani-b552b5221/" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"></path><rect x="2" y="9" width="4" height="12"></rect><circle cx="4" cy="4" r="2"></circle></svg>
            </a>
            <!-- <a href="https://twitter.com/tuouser" target="_blank" rel="noopener noreferrer" aria-label="Twitter/X">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M22 4s-.7 2.1-2 3.4c1.6 10-9.4 17.3-18 11.6 2.2.1 4.4-.6 6-2C3 15.5.5 9.6 3 5c2.2 2.6 5.6 4.1 9 4-.9-4.2 4-6.6 7-3.8 1.1 0 3-1.2 3-1.2z"></path></svg>
            </a>
            <a href="https://facebook.com/tuouser" target="_blank" rel="noopener noreferrer" aria-label="Facebook">
              <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path></svg>
            </a> -->
          </div>
        </div>
      </div>
      
    </div>
  </div>
</section>

<section class="section {fadeIn ? 'fade-in' : ''}">
  <div class="container">
    <h2 class="section-title">I Nostri Progetti</h2>
    <div class="row">
      <div class="col-6">
        <div class="card project-card">
          <img src="{base}/img/Abruzzo_verticale.jpg" alt="Abruzzo Verticale" class="card-image" />
          <h3 class="card-title">Abruzzo Verticale</h3>
          <p>La nostra community su WhatsApp dedicata agli appassionati di arrampicata, alpinisimo, trekking e eventi legati alla montagna in Abruzzo.</p>
          <a href="{base}/abruzzo-verticale" class="btn btn-primary">Scopri di più</a>
        </div>
      </div>
      <div class="col-6">
        <div class="card project-card">
          <img src="{base}/img/Cascata_di_San_Rocco.jpg" alt="Progetto Pescosansonesco" class="card-image" />
          <h3 class="card-title">Progetto Pescosansonesco</h3>
          <p>Iniziativa di riqualificazione dell'area naturale di Pescosansonesco con un nuovo sentiero escursionistico e area boulder.</p>
          <a href="{base}/progetto-pescosansonesco" class="btn btn-primary">Scopri di più</a>
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
                url('/img/Uomo_bouldering.jpg') center/cover no-repeat;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    color: white;
    margin-bottom: 3rem;
    opacity: 0;  
    transition: opacity 0.8s ease;
    overflow-x: hidden;
    &.fade-in {
      opacity: 1;
    }
    
    .hero-content {
      max-width: 800px;
      padding: 0 2rem;
      width: 100%;
    }
    
    h1 {
      font-size: 3rem;
      margin-bottom: 1rem;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
      word-wrap: break-word;
      
      @media (max-width: 768px) {
        font-size: 2.2rem;
      }
      
      @media (max-width: 480px) {
        font-size: 1.8rem;
      }
    }
    
    .hero-subtitle {
      font-size: 1.5rem;
      text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.5);
      
      @media (max-width: 768px) {
        font-size: 1.2rem;
      }
      
      @media (max-width: 480px) {
        font-size: 1rem;
      }
    }
  }
  
  .section {
    padding: 4rem 0;
    
    &.bg-light {
      background-color: #f8f9fa;
    }
  }
  
  .section-title {
    margin-bottom: 2rem;
    position: relative;
    
  }
  
  .row.justify-center {
    justify-content: center;
  }
  
  .img-fluid {
    max-width: 100%;
    height: auto;
  }
  
  .rounded {
    border-radius: 8px;
  }
  
  .team-card {
    text-align: center;
    padding: 2rem 1rem;
    height: 100%;
    
    .team-avatar {
      width: 120px;
      height: 120px;
      margin: 0 auto 1.5rem;
      border-radius: 50%;
      overflow: hidden;
      
    
      
      .avatar-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 50%;
      }
    }
    
    h3 {
      margin-bottom: 0.5rem;
    }
    
    .team-role {
      color: #3498db;
      font-weight: 600;
      margin-bottom: 1rem;
    }
    
    p {
      color: #666;
    }
    
    .social-icons {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 0.8rem;
      margin-top: 1.2rem;
      
      a {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 36px;
        height: 36px;
        border-radius: 50%;
        color: #555;
        transition: all 0.3s ease;
        background-color: #f0f0f0;
        
        &:hover {
          background-color: #3498db;
          color: white;
          transform: translateY(-2px);
        }
        
        @media (max-width: 768px) {
          width: 32px;
          height: 32px;
        }
        
        @media (max-width: 480px) {
          width: 28px;
          height: 28px;
          flex: 0 0 calc(33.3333% - 0.8rem);
          margin-bottom: 0.5rem;
        }
      }
    }
  }
  
  .project-card {
    height: 100%;
    display: flex;
    flex-direction: column;
    
    .card-image {
      width: 100%;
      height: 240px;
      object-fit: cover;
      border-radius: 8px 8px 0 0;
    }
    
    .card-title {
      margin: 1.5rem 0 1rem;
    }
    
    p {
      margin-bottom: 1.5rem;
      flex-grow: 1;
    }
    
    .btn {
      align-self: flex-start;
    }
  }
</style>
