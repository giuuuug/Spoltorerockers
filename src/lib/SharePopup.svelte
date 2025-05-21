<script lang="ts">
    export let showPopup: boolean = false;
    export let pageUrl: string = '';

    // Passato l'evento da parent component
    export let onClose: () => void = () => {};
    export let onCopy: () => void = () => {};
    export let onShare: (platform: string) => void = () => {};
    
    // Handle keyboard events
    function handleKeydown(event: KeyboardEvent) {
        if (event.key === 'Escape' && showPopup) {
            onClose();
        }
    }
</script>

<svelte:window on:keydown={handleKeydown} />

{#if showPopup}
    <div class="share-popup-overlay" on:click={onClose}>
        <div class="share-popup" on:click|stopPropagation role="dialog" aria-labelledby="share-popup-title" aria-modal="true">
            <div class="share-popup-header">
                <h3 id="share-popup-title">Condividi questa pagina</h3>
                <button class="close-btn" on:click={onClose} aria-label="Chiudi">
                    &times;
                </button>
            </div>
            <div class="share-popup-content">
                <div class="share-url">
                    <input type="text" readonly value={pageUrl} aria-label="URL da condividere" />
                    <button on:click={onCopy} aria-label="Copia l'URL negli appunti">Copia</button>
                </div>
                <div class="share-buttons">
                    <button 
                        class="share-btn whatsapp" 
                        on:click={() => onShare("whatsapp")}
                        aria-label="Condividi su WhatsApp"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="24"
                            height="24"
                            viewBox="0 0 24 24"
                            fill="currentColor"
                            aria-hidden="true"
                        >
                            <path
                                d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"
                            />
                        </svg>
                        WhatsApp
                    </button>
                    <button 
                        class="share-btn telegram" 
                        on:click={() => onShare("telegram")}
                        aria-label="Condividi su Telegram"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="24"
                            height="24"
                            viewBox="0 0 24 24"
                            fill="currentColor"
                            aria-hidden="true"
                        >
                            <path
                                d="M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z"
                            />
                        </svg>
                        Telegram
                    </button>
                    <button 
                        class="share-btn facebook" 
                        on:click={() => onShare("facebook")}
                        aria-label="Condividi su Facebook"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="24"
                            height="24"
                            viewBox="0 0 24 24"
                            fill="currentColor"
                            aria-hidden="true"
                        >
                            <path
                                d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"
                            />
                        </svg>
                        Facebook
                    </button>
                    <button 
                        class="share-btn instagram" 
                        on:click={() => onShare("instagram")}
                        aria-label="Condividi su Instagram"
                    >
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="24"
                            height="24"
                            viewBox="0 0 24 24"
                            fill="currentColor"
                            aria-hidden="true"
                        >
                            <path
                                d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"
                            />
                        </svg>
                        Instagram
                    </button>
                </div>
            </div>
        </div>
    </div>
{/if}

<style lang="scss">
    @use "sass:color";

    .share-popup-overlay {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.7);
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }

    .share-popup {
        background-color: white;
        border-radius: 8px;
        width: 90%;
        max-width: 500px;
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2);
        overflow: hidden;
    }

    .share-popup-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem;
        background: linear-gradient(135deg, #4e4c4f, #232220);
        color: white;

        h3 {
            margin: 0;
        }

        .close-btn {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            padding: 0;
            line-height: 1;
        }
    }

    .share-popup-content {
        padding: 1.5rem;
    }

    .share-url {
        display: flex;
        margin-bottom: 1.5rem;

        input {
            flex: 1;
            padding: 0.5rem;
            border: 1px solid #ddd;
            border-radius: 4px 0 0 4px;
            font-size: 0.9rem;
        }

        button {
            background-color: #232220;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 0 4px 4px 0;
            cursor: pointer;
            font-weight: 600;

            &:hover {
                background-color: color.adjust(#232220, $lightness: -10%);
            }
        }
    }

    .share-buttons {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 1rem;

        .share-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            padding: 0.75rem;
            border: none;
            border-radius: 4px;
            color: white;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;

            svg {
                width: 20px;
                height: 20px;
            }

            &.whatsapp {
                background-color: #25d366;
                &:hover {
                    background-color: color.adjust(#25d366, $lightness: -10%);
                }
            }

            &.telegram {
                background-color: #0088cc;
                &:hover {
                    background-color: color.adjust(#0088cc, $lightness: -10%);
                }
            }

            &.facebook {
                background-color: #1877f2;
                &:hover {
                    background-color: color.adjust(#1877f2, $lightness: -10%);
                }
            }

            &.instagram {
                background: linear-gradient(
                    45deg,
                    #405de6,
                    #5851db,
                    #833ab4,
                    #c13584,
                    #e1306c,
                    #fd1d1d
                );
                &:hover {
                    opacity: 0.9;
                }
            }
        }
    }

    @media (max-width: 576px) {
        .share-buttons {
            grid-template-columns: 1fr;
        }
    }
</style>
