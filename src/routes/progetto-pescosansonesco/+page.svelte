<script>
	import { onMount } from 'svelte';
	import { base } from '$app/paths';
	import SharePopup from '$lib/SharePopup.svelte';

	let fadeIn = false;
	let showSharePopup = false;
	let pageUrl = '';

	onMount(() => {
		setTimeout(() => {
			fadeIn = true;
		}, 100);

		// Ottieni l'URL corrente della pagina
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
				shareUrl = `https://wa.me/?text=${encodeURIComponent('Guarda il Progetto Pescosansonesco di Spoltorerockers: ' + pageUrl)}`;
				break;
			case 'telegram':
				shareUrl = `https://t.me/share/url?url=${encodeURIComponent(pageUrl)}&text=${encodeURIComponent('Guarda il Progetto Pescosansonesco di Spoltorerockers')}`;
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
		<h1>Progetto Pescosansonesco</h1>
		<p class="hero-subtitle">Riqualificazione dell'area naturale per l'arrampicata sostenibile</p>
	</div>
</div>


<section class="section">
	<div class="container">
		<div class="row">
			<div class="col-6">
				<h2 class="section-title">Il Progetto</h2>
				<p>
					Il Progetto Pescosansonesco di Spoltorerockers nasce dalla volontà di restituire nuova
					vita a un'area naturale di straordinaria bellezza, da tempo in stato di abbandono e
					riconquistata dalla vegetazione spontanea. Attraverso un meticoloso intervento di
					riqualificazione, miriamo a trasformare questo luogo in un'eccellenza per la pratica
					dell'arrampicata sportiva, nel pieno rispetto dell'ecosistema del Parco Nazionale della
					Majella.
				</p>
				<p>
					Il percorso escursionistico che abbiamo tracciato si snoda attraverso questo ambiente
					rinnovato, offrendo agli amanti della natura e dello sport scorci suggestivi. Un punto di
					particolare interesse lungo il cammino è rappresentato da un'area "boulder".
				</p>
				<p>
					L'itinerario culmina infine in uno spettacolo naturale mozzafiato: due fantastiche cascate
					che incorniciano l'area di arrampicata. Il nostro obiettivo è creare un polo attrattivo
					per tutti i livelli di arrampicatori, dai neofiti agli esperti, promuovendo al contempo un
					turismo sportivo sostenibile e la valorizzazione delle meraviglie naturali di
					Pescosansonesco.
				</p>
			</div>
			<div class="col-6">
				<img
					src="{base}/img/Cascata_di_San_Rocco.jpg"
					alt="Cascata di San Rocco"
					class="img-fluid rounded"
				/>
				<div class="project-stats">
					<div class="stat-item">
						<div class="stat-number">15+</div>
						<div class="stat-label">Vie di arrampicata</div>
					</div>
					<div class="stat-item">
						<div class="stat-number">3</div>
						<div class="stat-label">Settori</div>
					</div>
					<div class="stat-item">
						<div class="stat-number">10+</div>
						<div class="stat-label">Volontari</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>

<section class="section bg-light">
	<div class="container">
		<h2 class="section-title">Fasi del Progetto</h2>
		<div class="timeline">
			<div class="timeline-item">
				<div class="timeline-marker completed"></div>
				<div class="timeline-content">
					<h3>Fase 1: Esplorazione e Mappatura</h3>
					<p class="timeline-date">Completata - 10 Maggio 2025</p>
					<p>
						Esplorazione dell'area, individuazione dei settori potenziali e mappatura delle pareti
						rocciose adatte all'arrampicata.
					</p>
				</div>
			</div>
			<div class="timeline-item">
				<div class="timeline-marker completed"></div>
				<div class="timeline-content">
					<h3>Fase 2: Pulizia e Preparazione</h3>
					<p class="timeline-date">Completata - 18 Maggio 2025</p>
					<p>
						Pulizia delle pareti da vegetazione invasiva, rimozione di detriti e preparazione dei
						sentieri di accesso. Segnaletica bianco-rossa per i sentieri. Assegnazione gradi di
						difficolta per le vie boulder.
					</p>
				</div>
			</div>
			<!-- <div class="timeline-item">
				<div class="timeline-marker active"></div>
				<div class="timeline-content">
					<h3>Fase 3: Pulizia a fondo</h3>
					<p class="timeline-date">Prevista - Prevista </p>
					<p>Pulizia a fondo del sentiero, raccolta rifiuti e rimozione rami.</p>
				</div>
			</div> -->
		</div>
	</div>
</section>

<section class="section">
	<div class="container">
		<h2 class="section-title">Come Partecipare</h2>
		<div class="row">
			<div class="col-4">
				<div class="card participation-card">
					<div class="card-icon">
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
						Partecipa alle giornate di lavoro collettivo per la pulizia, la manutenzione e la
						chiodatura delle vie.
					</p>
					<a href="{base}/contatti" class="btn btn-primary">Volontariato</a>
				</div>
			</div>
			<div class="col-4">
				<div class="card participation-card">
					<div class="card-icon">
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
							<line x1="12" y1="1" x2="12" y2="23"></line>
							<path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"></path>
						</svg>
					</div>
					<h3>Donazione</h3>
					<p>
						Sostieni economicamente il progetto per l'acquisto di materiali, attrezzature e per la
						realizzazione della segnaletica.
					</p>
					<a href="{base}/dona" class="btn btn-primary">Dona Ora</a>
				</div>
			</div>
			<div class="col-4">
				<div class="card participation-card">
					<div class="card-icon">
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
						Aiutaci a far conoscere il progetto condividendo le informazioni sui social media e
						parlando con altri appassionati.
					</p>
					<!-- svelte-ignore a11y_invalid_attribute -->
					<a href="" class="btn btn-primary" on:click|preventDefault={toggleSharePopup}>
						Condividi</a>
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
			url('/img/Pescosansonesco.jpg') center/cover no-repeat;
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
				font-size: 1.7rem;
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

	.img-fluid {
		max-width: 100%;
		height: auto;
	}

	.rounded {
		border-radius: 8px;
	}

	.project-stats {
		display: flex;
		justify-content: space-between;
		margin-top: 2rem;
		text-align: center;

		.stat-item {
			flex: 1;
			padding: 1rem;

			.stat-number {
				font-size: 2.5rem;
				font-weight: 700;
				color: #d9ae8e;
				margin-bottom: 0.5rem;
			}

			.stat-label {
				font-size: 0.9rem;
				color: #666;
				text-transform: uppercase;
				letter-spacing: 1px;
			}
		}
	}

	.bg-light {
		background-color: #f8f9fa;
	}

	.timeline {
		position: relative;
		padding: 2rem 0;

		&::before {
			content: '';
			position: absolute;
			top: 0;
			left: 50px;
			height: 100%;
			width: 4px;
			background: #e9ecef;
			border-radius: 4px;
		}

		.timeline-item {
			position: relative;
			padding-left: 100px;
			margin-bottom: 3rem;

			&:last-child {
				margin-bottom: 0;
			}

			.timeline-marker {
				position: absolute;
				top: 0;
				left: 48px;
				width: 8px;
				height: 8px;
				border-radius: 50%;
				border: 4px solid #e9ecef;
				background-color: white;
				transform: translateX(-50%);

				&.completed {
					background-color: #27ae60;
					border-color: #27ae60;
				}

				&.active {
					background-color: white;
					border-color: #3498db;
				}
			}

			.timeline-content {
				background-color: white;
				padding: 1.5rem;
				border-radius: 8px;
				box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);

				h3 {
					margin-bottom: 0.5rem;
				}

				.timeline-date {
					color: #666;
					font-size: 0.9rem;
					margin-bottom: 1rem;
					font-style: italic;
				}
			}
		}
	}

	.participation-card {
		text-align: center;
		height: 100%;
		display: flex;
		flex-direction: column;
		.card-icon {
			margin: 0 auto 1.5rem;
			width: 80px;
			height: 80px;
			background: linear-gradient(135deg, #3498db, #8e44ad);
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
</style>
