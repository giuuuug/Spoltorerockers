<script>
  // Props for social media links - user can update these
  export let instagramLink = "https://instagram.com/spoltorerockers";
  export let facebookLink = "https://facebook.com/spoltorerockers";
  export let tiktokLink = "https://tiktok.com/@spoltore.rockers";
  export let whatsappLink = "https://chat.whatsapp.com/HwoIrojkiDKAUgEGKdpuqO";
</script>

<footer>
  <div class="footer-content">
    <p>Spoltorerockers, Abruzzo, Italia</p>
    <div class="social-links">
      <a href={instagramLink} target="_blank" rel="noopener noreferrer" aria-label="Instagram">
        <svg xmlns="http://www.w3.org/2000/svg" class="icon" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <rect x="2" y="2" width="20" height="20" rx="5" ry="5"></rect>
          <path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"></path>
          <line x1="17.5" y1="6.5" x2="17.51" y2="6.5"></line>
        </svg>
      </a>
      <a href={facebookLink} target="_blank" rel="noopener noreferrer" aria-label="Facebook">
        <svg xmlns="http://www.w3.org/2000/svg" class="icon" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z"></path>
        </svg>
      </a>
      <a href={tiktokLink} target="_blank" rel="noopener noreferrer" aria-label="TikTok">
        <svg xmlns="http://www.w3.org/2000/svg" class="icon" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M9 12a4 4 0 1 0 4 4V4a5 5 0 0 0 5 5"></path>
        </svg>
      </a>
      <a href={whatsappLink} target="_blank" rel="noopener noreferrer" aria-label="WhatsApp">
        <svg xmlns="http://www.w3.org/2000/svg" class="icon" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
          <path d="M21 11.5a8.38 8.38 0 0 1-.9 3.8 8.5 8.5 0 0 1-7.6 4.7 8.38 8.38 0 0 1-3.8-.9L3 21l1.9-5.7a8.38 8.38 0 0 1-.9-3.8 8.5 8.5 0 0 1 4.7-7.6 8.38 8.38 0 0 1 3.8-.9h.5a8.48 8.48 0 0 1 8 8v.5z"></path>
        </svg>
      </a>
    </div>
  </div>
</footer>

<style>
  footer {
    background-color: #2c3e50; /* Dark gray - a bit more bluish */
    color: #ecf0f1; /* Light text for contrast */
    padding: 25px 0;
    text-align: center;
    font-family: 'Helvetica Neue', Arial, sans-serif; /* Professional font stack */
    opacity: 0.98; /* Slightly opaque */
    width: 100%;
    margin-top: auto; /* Pushes footer to the bottom if content is short */
    border-top: 1px solid #34495e; /* Subtle top border */
  }

  .footer-content {
    max-width: 1100px;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px; /* Spacing between text and social links */
  }

  .footer-content p {
    margin: 0;
    font-size: 0.95em;
  }

  .social-links a {
    color: #ecf0f1;
    text-decoration: none;
    margin: 0 12px;
    font-size: 1.4em; /* Icon size - adjust as needed */
    transition: color 0.3s ease;
  }

  .social-links a:hover {
    color: #bdc3c7; /* Lighter gray on hover */
  }

  .icon {
    width: 24px;
    height: 24px;
    transition: transform 0.2s ease;
  }

  .social-links a:hover .icon {
    transform: scale(1.1);
  }

  /* Responsive adjustments */
  @media (min-width: 768px) {
    .footer-content {
      flex-direction: row;
      justify-content: space-between;
      padding: 0 25px; /* Add some horizontal padding on larger screens */
    }
     .social-links {
      margin-left: 20px; /* Ensure some space from the text on the left */
    }
  }
</style>
