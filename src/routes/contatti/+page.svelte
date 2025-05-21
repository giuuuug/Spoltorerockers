<script>
	import { onMount } from 'svelte';
	import { base } from '$app/paths';

	let fadeIn = false;
	let formData = {
		name: '',
		email: '',
		subject: '',
		message: ''
	};

	onMount(() => {
		setTimeout(() => {
			fadeIn = true;
		}, 100);
	});

	/**
	 * @param {{ preventDefault: () => void; }} event
	 */
	function handleSubmit(event) {
		event.preventDefault();

		// Prepare email content
		const mailtoLink = `mailto:spoltorerockers@gmail.com?subject=${encodeURIComponent(formData.subject)}&body=${encodeURIComponent(
			`${formData.message}` + `\n\n` + `Nome: ${formData.name}\n`
		)}`;

		// Open default email client
		window.location.href = mailtoLink;
	}
</script>

<div class="hero {fadeIn ? 'fade-in' : ''}">
	<div class="hero-content">
		<h1>Contatti</h1>
		<p class="hero-subtitle">Resta in contatto con il team di Spoltorerockers</p>
	</div>
</div>

<section class="section">
	<div class="container">
		<div class="row">
			<div class="col-6">
				<div class="card contact-card">
					<h2 class="section-title">Informazioni di Contatto</h2>
					<div class="contact-info">
						<div class="contact-item">
							<div class="contact-icon">
								<svg
									xmlns="http://www.w3.org/2000/svg"
									width="24"
									height="24"
									viewBox="0 0 24 24"
									fill="none"
									stroke="currentColor"
									stroke-width="2"
									stroke-linecap="round"
									stroke-linejoin="round"
								>
									<path
										d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"
									></path>
								</svg>
							</div>
							<div class="contact-text">
								<h3>Telefono</h3>
								<p>+39 389 133 8962</p>
							</div>
						</div>
						<div class="contact-item">
							<div class="contact-icon">
								<svg
									xmlns="http://www.w3.org/2000/svg"
									width="24"
									height="24"
									viewBox="0 0 24 24"
									fill="none"
									stroke="currentColor"
									stroke-width="2"
									stroke-linecap="round"
									stroke-linejoin="round"
								>
									<path
										d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"
									></path>
									<polyline points="22,6 12,13 2,6"></polyline>
								</svg>
							</div>
							<div class="contact-text">
								<h3>Email</h3>
								<p>spoltorerockers@gmail.com</p>
							</div>
						</div>
						<!-- <div class="contact-item">
              <div class="contact-icon">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path>
                  <circle cx="12" cy="10" r="3"></circle>
                </svg>
              </div>
              <div class="contact-text">
                <h3>Indirizzo</h3>
                <p>Via dell'Arrampicata, 42<br>65010 Spoltore (PE)<br>Abruzzo, Italia</p>
              </div>
            </div> -->
						<div class="contact-item">
							<div class="contact-icon">
								<svg
									xmlns="http://www.w3.org/2000/svg"
									width="24"
									height="24"
									viewBox="0 0 24 24"
									fill="none"
									stroke="currentColor"
									stroke-width="2"
									stroke-linecap="round"
									stroke-linejoin="round"
								>
									<rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
									<path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
									<line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
								</svg>
							</div>
							<div class="contact-text">
								<h3>Social</h3>
								<div class="social-links">
									<a href="https://instagram.com/spoltorerockers" class="social-link" aria-label="Instagram">
										<svg viewBox="0 0 24 24" class="social-icon">
											<path fill="currentColor" d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z"/>
										</svg>
									</a>
									<a href="https://facebook.com/spoltorerockers" class="social-link" aria-label="Facebook">
										<svg viewBox="0 0 24 24" class="social-icon">
											<path fill="currentColor" d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/>
										</svg>
									</a>
									<a href="https://tiktok.com/@spoltorerockers" class="social-link" aria-label="TikTok">
										<svg viewBox="0 0 24 24" class="social-icon">
											<path fill="currentColor" d="M19.59 6.69a4.83 4.83 0 0 1-3.77-4.25V2h-3.45v13.67a2.89 2.89 0 0 1-5.2 1.74 2.89 2.89 0 0 1 2.31-4.64 2.93 2.93 0 0 1 .88.13V9.4a6.84 6.84 0 0 0-1-.05A6.33 6.33 0 0 0 5 20.1a6.34 6.34 0 0 0 10.86-4.43v-7a8.16 8.16 0 0 0 4.77 1.52v-3.4a4.85 4.85 0 0 1-1-.1z"/>
										</svg>
									</a>
									<a href="https://chat.whatsapp.com/HwoIrojkiDKAUgEGKdpuqO" class="social-link" aria-label="WhatsApp">
										<svg viewBox="0 0 24 24" class="social-icon">
											<path fill="currentColor" d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
										</svg>
									</a>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
			<div class="col-6">
				<div class="card">
					<h2 class="section-title">Scrivici</h2>
					<form class="contact-form" on:submit={handleSubmit}>
						<div class="form-group">
							<label for="name">Nome</label>
							<input
								type="text"
								id="name"
								name="name"
								bind:value={formData.name}
								placeholder="Il tuo nome"
								required
							/>
						</div>
						<div class="form-group">
							<label for="email">Email</label>
							<input
								type="email"
								id="email"
								name="email"
								bind:value={formData.email}
								placeholder="La tua email"
								required
							/>
						</div>
						<div class="form-group">
							<label for="subject">Oggetto</label>
							<input
								type="text"
								id="subject"
								name="subject"
								bind:value={formData.subject}
								placeholder="Oggetto del messaggio"
							/>
						</div>
						<div class="form-group">
							<label for="message">Messaggio</label>
							<textarea
								id="message"
								name="message"
								bind:value={formData.message}
								rows="5"
								placeholder="Il tuo messaggio"
								required
							></textarea>
						</div>
						<button type="submit" class="btn btn-primary">
              <span>Invia Messaggio</span>
            </button>
					</form>
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
                url('/img/Contattaci.jpg') center/cover no-repeat;
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

	.contact-card {
		height: 100%;
	}

	.contact-info {
		margin-top: 1.5rem;
	}

	.contact-item {
		display: flex;
		margin-bottom: 1.5rem;

		.contact-icon {
			flex: 0 0 50px;
			height: 50px;
			background: linear-gradient(135deg, #2c3e50, #3498db);
			border-radius: 50%;
			display: flex;
			align-items: center;
			justify-content: center;
			color: white;
			margin-right: 1rem;
		}

		.contact-text {
			flex: 1;

			h3 {
				font-size: 1.2rem;
				margin-bottom: 0.5rem;
			}

			p {
				color: #666;
				margin-bottom: 0;
			}
		}
	}

	.social-links {
		display: flex;
		gap: 1rem;

		.social-link {
			color: #3498db;
			text-decoration: none;
			font-weight: 500;
			transition: color 0.3s;

			&:hover {
				color: #2c3e50;
			}
		}

		.social-icon {
			width: 24px;
			height: 24px;
		}
	}

	.contact-form {
		.form-group {
			margin-bottom: 1.5rem;

			label {
				display: block;
				margin-bottom: 0.5rem;
				font-weight: 500;
			}

			input,
			textarea {
				width: 100%;
				padding: 0.75rem;
				border: 1px solid #ddd;
				border-radius: 4px;
				font-family: inherit;
				font-size: 1rem;
				transition: border-color 0.3s;

				&:focus {
					outline: none;
					border-color: #3498db;
				}
			}
		}

		button {
			width: 100%;
		}
	}
</style>
