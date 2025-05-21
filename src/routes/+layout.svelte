<script>
  import { onMount } from 'svelte';
  import { base } from '$app/paths';
  import '../app.scss';
  import Footer from '$lib/Footer.svelte';
  
  let menuOpen = false;
  let isMobile = false;
  
  function toggleMenu() {
    menuOpen = !menuOpen;
  }
  
  onMount(() => {
    const checkMobile = () => {
      isMobile = window.innerWidth < 768;
      if (!isMobile) menuOpen = false;
    };
    
    checkMobile();
    window.addEventListener('resize', checkMobile);
    
    return () => {
      window.removeEventListener('resize', checkMobile);
    };
  });
</script>

<div class="app-container">  <header>
    <a href="{base}/" class="logo-container">
      <img src="{base}/img/Logo.png" alt="Spoltorerockers Logo" class="logo" />
      <h1>Spoltorerockers</h1>
    </a>
    <button class="menu-toggle" on:click={toggleMenu} aria-label="Toggle menu">
      <svg xmlns="http://www.w3.org/2000/svg" class="menu-icon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
        <line x1="3" y1="12" x2="21" y2="12"></line>
        <line x1="3" y1="6" x2="21" y2="6"></line>
        <line x1="3" y1="18" x2="21" y2="18"></line>
      </svg>
    </button>
  </header>
    {#if menuOpen}
    <div 
      class="overlay" 
      role="button"
      tabindex="0"
      on:click={toggleMenu}
      on:keydown={e => e.key === 'Escape' && toggleMenu()}
      aria-label="Chiudi menu"
    ></div>
  {/if}
  
  <div class="content-wrapper">
    <nav class={`sidebar ${menuOpen ? 'open' : ''}`}>
      <div class="nav-header">
        <button class="close-menu" on:click={toggleMenu} aria-label="Chiudi menu">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" class="close-icon">
            <line x1="18" y1="6" x2="6" y2="18"></line>
            <line x1="6" y1="6" x2="18" y2="18"></line>
          </svg>
        </button>
      </div>
      <ul>
        <li><a href="{base}/" on:click={toggleMenu}>Home</a></li>
        <li><a href="{base}/contatti" on:click={toggleMenu}>Contatti</a></li>
        <li><a href="{base}/abruzzo-verticale" on:click={toggleMenu}>Abruzzo Verticale</a></li>
        <li><a href="{base}/progetto-pescosansonesco" on:click={toggleMenu}>Progetto Pescosansonesco</a></li>
        <li><a href="{base}/dona" on:click={toggleMenu}>Dona</a></li>
      </ul>
    </nav>
    
    <main class="content">
      <slot />
    </main>
  </div>
</div>

<Footer />

<style lang="scss">
  @use "sass:color";
  
  .app-container {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    position: relative;
    overflow-x: hidden;
  }
    header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 100;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    
    .logo-container {
      display: flex;
      align-items: center;
      text-decoration: none;
      cursor: pointer;
      
      .logo {
        height: 40px;
        width: 40px;
        margin-right: 1rem;
        border-radius: 50%;
        object-fit: cover;
      }
      
      h1 {
        font-size: 1.5rem;
        margin: 0;
        color: $light-sand;
      }
    }
  }
  
  .menu-toggle {
    display: flex;
    align-items: center;
    justify-content: center;
    border: none;
    cursor: pointer;
    padding: 0.5rem;
    z-index: 10;
    
    .menu-icon {
      width: 24px;
      height: 24px;
      color: $sand;
    }

    &:hover .menu-icon {
      color: $light-sand; 
    }
  }
  
  .overlay {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: rgba($dark, 0.5);
    z-index: 998;
    backdrop-filter: blur(2px);
  }
  
  .content-wrapper {
    display: flex;
    flex: 1;
    margin-top: 72px;
  }
  
  .sidebar {
    position: fixed;
    top: 0;
    right: -300px;
    width: 300px;
    height: 100vh;
    padding: 1rem 0;
    z-index: 999;
    transition: right 0.3s ease-in-out;
    overflow-y: auto;
    
    &.open {
      right: 0;
    }
    
    .nav-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 1rem 1rem;
      border-bottom: 1px solid rgba($light-sand, 0.1);
      margin-bottom: 1rem;
      
      .nav-logo {
        height: 40px;
        border-radius: 50%;
        object-fit: cover;
      }
      
      .close-menu {
        border: none;
        color: $light-sand;
        cursor: pointer;
        padding: 0.5rem;
        
        .close-icon {
          width: 24px;
          height: 24px;
        }
      }
    }
    
    ul {
      list-style: none;
      padding: 0;
      margin: 0;
      
      li {
        a {
          display: block;
          padding: 1rem 1.5rem;
          color: $sand; /* Cambiato per migliorare il contrasto */
          text-decoration: none;
          transition: all 0.3s;
          border-left: 3px solid transparent;
          
          &:hover, &:focus {
            color: $light-sand;
            background-color: rgba($gray-dark, 0.3);
            border-left-color: $sand;
            padding-left: 2rem;
          }
        }
      }
    }
  }
  
  .content {
    flex: 1;
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
    width: 100%;
  }
</style>