<script>
  export let isOpen;
  export let onClose;
</script>

{#if isOpen}
  <div class="modal-backdrop" on:click={onClose}></div>
  <div class="modal">
    <button class="close-button" on:click={onClose}>×</button>
    <h2>About</h2>
    <p>
      This project is a demonstration of a full-screen image carousel using
      Svelte. The images are generated with the same AI prompt, focusing on
      different countries. Each image has a unique view through the same prompt,
      showcasing the versatility of the AI. Technologies used include Svelte for
      the frontend framework and CSS for styling and transitions.
    </p>
  </div>
{/if}

<style>
  .modal-backdrop {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.3);
    z-index: 999;
  }

  .modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    transition:
      width 0.3s ease,
      height 0.3s ease;
    background: rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(10px);
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.4);
    z-index: 1000;
    max-width: 500px;
    width: 80%;
    color: white;
  }

  .close-button {
    position: absolute;
    top: 10px;
    right: 10px;
    background: none;
    border: none;
    font-size: 20px;
    cursor: pointer;
    color: white;
  }

  h2 {
    margin: 0 0 10px 0;
  }

  p {
    margin: 0;
  }
</style>
