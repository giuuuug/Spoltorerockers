<script>
	import { onMount } from 'svelte';
	import { base } from '$app/paths';
	import SharePopup from '$lib/SharePopup.svelte';
	import GoFundMeWidget from '$lib/GoFundMe.svelte';

	let fadeIn = false;
	let showSharePopup = false;
	let pageUrl = '';

	onMount(() => {
		setTimeout(() => {
			fadeIn = true;
		}, 100);

		pageUrl = window.location.href;
	});

	function toggleSharePopup() {
		showSharePopup = !showSharePopup;
	}

	function copyToClipboard() {
		navigator.clipboard
			.writeText(pageUrl)
			.then(() => {
				alert('Link copiato negli appunti!');
			})
			.catch((err) => {
				console.error('Errore durante la copia: ', err);
			});
	}

	/**
	 * @param {string} platform
	 */
	function shareOnSocial(platform) {
		let shareUrl = '';

		switch (platform) {
			case 'whatsapp':
				shareUrl = `https://wa.me/?text=${encodeURIComponent('Sostieni il Progetto Pescosansonesco di Spoltorerockers: ' + pageUrl)}`;
				break;
			case 'telegram':
				shareUrl = `https://t.me/share/url?url=${encodeURIComponent(pageUrl)}&text=${encodeURIComponent('Sostieni il Progetto Pescosansonesco di Spoltorerockers')}`;
				break;
			case 'facebook':
				shareUrl = `https://www.facebook.com/sharer/sharer.php?u=${encodeURIComponent(pageUrl)}`;
				break;
			case 'instagram':
				// Instagram non ha un'API diretta per la condivisione, quindi copiamo negli appunti
				copyToClipboard();
				alert(
					'Instagram non supporta la condivisione diretta di link. Il link è stato copiato negli appunti!'
				);
				return;
		}

		window.open(shareUrl, '_blank');
	}
</script>

<div class="hero {fadeIn ? 'fade-in' : ''}">
	<div class="hero-content">
		<h1>Sostieni Spoltorerockers</h1>
		<p class="hero-subtitle">Il tuo contributo è fondamentale per i nostri progetti</p>
	</div>
</div>

<section class="section">
	<div class="container">
		<div class="row">
			<div class="col-5">
				<h2 class="section-title">Perché Donare</h2>
				<p>
					Spoltorerockers è un gruppo di appassionati che lavora per promuovere l'arrampicata in
					Abruzzo e valorizzare il territorio montano della regione. Tutti i nostri progetti sono
					realizzati grazie al lavoro volontario e alle donazioni di chi crede nella nostra
					missione.
				</p>
				<p>La tua donazione ci aiuterà a:</p>
				<ul class="donation-uses">
					<li>
						<div class="use-icon">
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
									d="M20.59 13.41l-7.17 7.17a2 2 0 0 1-2.83 0L2 12V2h10l8.59 8.59a2 2 0 0 1 0 2.82z"
								></path>
								<line x1="7" y1="7" x2="7.01" y2="7"></line>
							</svg>
						</div>
						<div class="use-text">
							<h4>Acquistare Materiali</h4>
							<p>
								Chiodi, protezioni, corde e attrezzature per la messa in sicurezza delle vie di
								arrampicata
							</p>
						</div>
					</li>
					<li>
						<div class="use-icon">
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
								<rect x="3" y="3" width="18" height="18" rx="2" ry="2"></rect>
								<line x1="3" y1="9" x2="21" y2="9"></line>
								<line x1="9" y1="21" x2="9" y2="9"></line>
							</svg>
						</div>
						<div class="use-text">
							<h4>Creare Segnaletica</h4>
							<p>
								Realizzare pannelli informativi e segnaletica per i sentieri e le aree di
								arrampicata
							</p>
						</div>
					</li>
					<li>
						<div class="use-icon">
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
								<path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"></path>
								<circle cx="9" cy="7" r="4"></circle>
								<path d="M23 21v-2a4 4 0 0 0-3-3.87"></path>
								<path d="M16 3.13a4 4 0 0 1 0 7.75"></path>
							</svg>
						</div>
						<div class="use-text">
							<h4>Organizzare Eventi</h4>
							<p>Promuovere incontri, workshop e giornate di formazione per la community</p>
						</div>
					</li>
				</ul>
			</div>
		</div>
	</div>
</section>

<section class="section">
	<div class="container">
		<h2 class="section-title">Raccolte fondi</h2>
		<div class="row">
			<div class="col-6">
				<!--
            <div class="project-card completed">
            <div class="project-status completed">Completato</div>
            -->
				<div class="project-card active">
					<div class="project-status active">Attivo</div>
					<GoFundMeWidget />
				</div>
			</div>
		</div>
	</div>
</section>

<section class="section">
	<div class="container">
		<h2 class="section-title">Altri Modi per Sostenerci</h2>
		<div class="row">
			<div class="col-4">
				<div class="card support-card">
					<div class="support-icon">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							width="40"
							height="40"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
						>
							<path
								d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"
							></path>
						</svg>
					</div>
					<h3>Volontariato</h3>
					<p>
						Unisciti al nostro team di volontari e partecipa attivamente ai progetti di
						Spoltorerockers.
					</p>
					<a href="{base}/contatti" class="btn btn-primary">Contattaci</a>
				</div>
			</div>
			<div class="col-4">
				<div class="card support-card">
					<div class="support-icon">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							width="40"
							height="40"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
						>
							<circle cx="12" cy="12" r="10"></circle>
							<line x1="2" y1="12" x2="22" y2="12"></line>
							<path
								d="M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10 15.3 15.3 0 0 1 4-10z"
							></path>
						</svg>
					</div>
					<h3>Diventa Partner</h3>
					<p>
						Se hai un'azienda o un'attività commerciale, diventa partner ufficiale dei nostri
						progetti.
					</p>
					<a href="{base}/contatti" class="btn btn-primary">Contattaci</a>
				</div>
			</div>
			<div class="col-4">
				<div class="card support-card">
					<div class="support-icon">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							width="40"
							height="40"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
						>
							<path
								d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"
							></path>
						</svg>
					</div>
					<h3>Condividi</h3>
					<p>
						Aiutaci a diffondere la nostra missione condividendo i nostri progetti sui social media.
					</p>
					<a
						href="{base}/#"
						class="btn btn-primary"
						on:click|preventDefault={toggleSharePopup}>Condividi</a
					>
				</div>
			</div>
		</div>
	</div>
</section>

{#if showSharePopup}
	<SharePopup
		showPopup={showSharePopup}
		{pageUrl}
		onClose={toggleSharePopup}
		onCopy={copyToClipboard}
		onShare={shareOnSocial}
	/>
{/if}

<style lang="scss">
	@use 'sass:color';
	.hero {
		height: 70vh;
		background:
			linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
			url('/img/Dona.png') center/cover no-repeat;
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

	.donation-uses {
		list-style: none;
		padding: 0;
		margin-top: 2rem;

		li {
			display: flex;
			margin-bottom: 1.5rem;

			.use-icon {
				flex: 0 0 50px;
				height: 50px;
				background: linear-gradient(135deg, #f39c12, #e74c3c);
				border-radius: 50%;
				display: flex;
				align-items: center;
				justify-content: center;
				color: white;
				margin-right: 1rem;
			}

			.use-text {
				flex: 1;

				h4 {
					font-size: 1.1rem;
					margin-bottom: 0.5rem;
				}

				p {
					color: #666;
					margin-bottom: 0;
				}
			}
		}
	}

	.project-card {
		position: relative;
		background-color: white;
		border-radius: 8px;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
		padding: 2rem;
		overflow: hidden;

		.project-status {
			position: absolute;
			top: 1rem;
			right: 1rem;
			padding: 0.25rem 0.75rem;
			border-radius: 20px;
			font-size: 0.8rem;
			font-weight: 600;

			&.active {
				background-color: #4caf50;
				color: white;
			}	
		}
	}

	

	.support-card {
		text-align: center;
		height: 100%;
		display: flex;
		flex-direction: column;

		.support-icon {
			margin: 0 auto 1.5rem;
			width: 80px;
			height: 80px;
			background: linear-gradient(135deg, #f39c12, #e74c3c);
			border-radius: 50%;
			display: flex;
			align-items: center;
			justify-content: center;
			color: white;
		}

		h3 {
			margin-bottom: 1rem;
		}

		p {
			margin-bottom: 1.5rem;
			flex-grow: 1;
		}
	}

	:global(.gfm-embed) {
		width: 100% !important;
		max-width: 100% !important;
	}

	:global(.gfm-embed iframe) {
		width: 100% !important;
		min-height: 400px !important;
	}
</style>
