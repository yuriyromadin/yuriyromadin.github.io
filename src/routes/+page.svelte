<svelte:head>
  <title>Yuriy Romadin - CTO at Sellfy</title>
</svelte:head>

<section>
  <div>
    <h1>Yuriy <br>Romadin</h1>
    <h2>
      <span>CTO <span class="small">@</span> <a href="https://sellfy.com/about/" target="_blank">Sellfy</a></span>

      <span class="socials">
        <a class="icon" href="https://www.linkedin.com/in/yuriyromadin/" aria-label="Yuriy Romadin's Linkedin profile" target="_blank">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M19 3a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2zm-.5 15.5v-5.3a3.26 3.26 0 0 0-3.26-3.26c-.85 0-1.84.52-2.32 1.3v-1.11h-2.79v8.37h2.79v-4.93c0-.77.62-1.4 1.39-1.4a1.4 1.4 0 0 1 1.4 1.4v4.93zM6.88 8.56a1.68 1.68 0 0 0 1.68-1.68c0-.93-.75-1.69-1.68-1.69a1.69 1.69 0 0 0-1.69 1.69c0 .93.76 1.68 1.69 1.68m1.39 9.94v-8.37H5.5v8.37z"/></svg>
        </a>

        <a class="icon" href="https://www.instagram.com/yuriyromadin/" aria-label="Yuriy Romadin's Instagram profile" target="_blank">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M7.8 2h8.4C19.4 2 22 4.6 22 7.8v8.4a5.8 5.8 0 0 1-5.8 5.8H7.8C4.6 22 2 19.4 2 16.2V7.8A5.8 5.8 0 0 1 7.8 2m-.2 2A3.6 3.6 0 0 0 4 7.6v8.8C4 18.39 5.61 20 7.6 20h8.8a3.6 3.6 0 0 0 3.6-3.6V7.6C20 5.61 18.39 4 16.4 4zm9.65 1.5a1.25 1.25 0 0 1 1.25 1.25A1.25 1.25 0 0 1 17.25 8A1.25 1.25 0 0 1 16 6.75a1.25 1.25 0 0 1 1.25-1.25M12 7a5 5 0 0 1 5 5a5 5 0 0 1-5 5a5 5 0 0 1-5-5a5 5 0 0 1 5-5m0 2a3 3 0 0 0-3 3a3 3 0 0 0 3 3a3 3 0 0 0 3-3a3 3 0 0 0-3-3"/></svg>
        </a>

        <a class="icon" href="mailto:yuriy@romadin.eu" aria-label="Yuriy Romadin's personal email">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M19.07 13.88L13 19.94V22h2.06l6.06-6.07m1.58-2.35l-1.28-1.28a.52.52 0 0 0-.38-.17c-.15.01-.29.06-.39.17l-1 1l2.05 2l1-1c.19-.2.19-.52 0-.72M11 18H4V8l8 5l8-5v2h2V6c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h7zm9-12l-8 5l-8-5z"/></svg>
        </a>
      </span>
    </h2>
  </div>

  <div class="shape-container">
    <div class="shape"/>
  </div>
</section>

<style>
section {
    display: flex;
    height: 100vh;
    align-items: center;
    justify-content: center;
  }
  div {
    max-width: 1000px;
    width: fit-content;
    margin-top: -5%;
  }
  .small {
    font-size: 18px;
  }
  br {
    display: none;
  }
  a {
    color: inherit;
  }
  h1 {
    font-size: clamp(2rem, 12.5vw, 6rem);
    text-transform: uppercase;
    text-shadow: 1px 0px 30px rgba(255, 255, 255, .2);
    margin: 0;
  }
  h2 {
    font-size: clamp(1rem, 0.5vw, 1.25rem);
    margin: 0;
    display: flex;
    align-items: center;
    font-weight: 400;
    gap: 20px;
  }

  h2 .icon {
    font-size: 0;
  }

  .socials {
    display: flex;
    gap: 10px;
    align-items: center;
  }

  .shape-container{
    display: flex;
    align-items: center;
    justify-content: center;
    height:100vh;
    position: fixed;
    width: 60vw;
    left: 45vw;
    z-index: -1;
    animation: move 200s linear infinite;
  }

  .shape{
    width: 45vw;
    height: 45vw;
    background: linear-gradient(64deg, #89CFF0 23%, #0077B6 50%, #000080 80%);
    mask-image: radial-gradient(circle, #000 10%, transparent 10%);
    mask-size: 1px 14px;

    border-radius: 28% 72% 22% 78% / 39% 23% 77% 61%;
    transform: rotate(0deg);
    will-change: border-radius, transform;

    animation: blob 10s linear infinite, spin 200s linear infinite;
  }

  @keyframes blob {
    0%, 100% {
      border-radius: 28% 72% 22% 78% / 39% 23% 77% 61%;
    }
    50% {
      border-radius: 72% 28% 50% 50% / 55% 26% 74% 45%;
    }
  }

  @keyframes spin {
    0% {
      transform: rotate(0deg);
    }
    100% {
      transform: rotate(359deg);
    }
  }

  @keyframes move {
    0%, 100% {
      transform: translateX(0);
    }
    50% {
      transform: translateX(-45vw);
    }
  }

  @media (max-width: 600px) {
    section {
      height: 80vh;
    }
    h1{
      margin-bottom: 1.5rem;
      font-size: clamp(2rem, 20vw, 6rem);
    }
    .socials {
      gap: 1.5rem;
    }
    br {
      display: block;
    }
    .shape {
      width: 95vw;
      height: 95vw;
    }
  }

</style>
