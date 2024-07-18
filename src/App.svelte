<script>
  import Header from './components/Header.svelte';
  import ImageCarousel from './components/ImageCarousel.svelte';
  import Modal from './components/Modal.svelte';

  let isModalOpen = false;

  function openModal() {
    isModalOpen = true;
  }

  function closeModal() {
    isModalOpen = false;
  }
</script>

<Header></Header>
<ImageCarousel></ImageCarousel>
<button class="info-button" on:click={openModal}>About</button>
<Modal isOpen={isModalOpen} onClose={closeModal}></Modal>

<style>
  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: rgba(0, 0, 0, 0.5);
    color: white;
    padding: 1rem;
    z-index: 2;
  }

  .carousel-container {
    position: relative;
    width: 100%;
    height: 100vh; /* Utiliza a altura total da tela */
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1; /* Garante que o carrossel fique abaixo do header */
  }

  .info-button {
    position: fixed;
    bottom: 10px;
    left: 10px;
    background: rgba(0, 0, 0, 0.5);
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    z-index: 1001;
  }

  .info-button:hover {
    background-color: rgba(0, 0, 0, 0.7);
  }
</style>
