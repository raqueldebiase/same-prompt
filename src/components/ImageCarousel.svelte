<script>
  let currentIndex = 0;
  let images = [
    {
      path: '/carousel/swiss.png',
      label: 'Swiss Mountains',
      text: 'A tranquil and picturesque... pastel-colored illustration of a quaint Germany countryside medieval town. The town is nestled between rolling hills, featuring charming cobblestone streets and vividly colored buildings that exude a timeless charm. The clear blue sky above sets the stage for a perfect spring morning, with a few stray birds gracefully soaring through the air. The serene atmosphere is further accentuated by the absence of people, creating an idyllic and peaceful scene that transcends time.',
    },
    {
      path: '/carousel/a-mesmerizing-pastel-colored-illustration-of-a-qua-QsRZ0VVrTmOIDLkAThRAkw-dLDrtnEaTTetxPFpagZZVw.png',
      label: 'Frenchside',
      text: 'A quaint french countryside... medieval town and picturesque pastel-colored illustration. The town is nestled between rolling hills, featuring charming cobblestone streets and vividly colored buildings that exude a timeless charm. The clear blue sky above sets the stage for a perfect spring morning, with a few stray birds gracefully soaring through the air. The serene atmosphere is further accentuated by the absence of people, creating an idyllic and peaceful scene that transcends time.',
    },
    {
      path: '/carousel/italian.png',
      label: 'Italian view',
      text: 'A captivating pastel-colored... illustration portrays a picturesque Italian countryside medieval town during a serene summer. The town, nestled among verdant rolling hills, showcases delightful pastel-hued buildings and enchanting cobblestone streets. The clear blue sky overhead adds depth to the idyllic setting, with a few graceful birds soaring through the air. The scenes tranquility is heightened by the absence of people, transporting the viewer to a timeless, peaceful era of solitude and nostalgia.',
    },
    {
      path: '/carousel/a-tranquil-and-picturesque-pastel-colored-illustra-zugmORi3R0i_kBGR6O1qvg-N3Epz3wWQp6veoMrNRwb9A.png',
      label: 'Austrian street',
      text: 'A captivating pastel-colored... illustration portrays a picturesque Austrian countryside medieval town during a serene summer. The town, nestled among verdant rolling hills, showcases delightful pastel-hued buildings and enchanting cobblestone streets. The clear blue sky overhead adds depth to the idyllic setting, with a few graceful birds soaring through the air. The scenes tranquility is heightened by the absence of people, transporting the viewer to a timeless, peaceful era of solitude and nostalgia.',
    },
    {
      path: '/carousel/a-serene-and-enchanting-pastel-colored-illustratio-YuT08wnbTeSY6vkA07wdkw-3Jr0-uIhSruMrk5eykFwZg.png',
      label: 'England countryside',
      text: 'A captivating and serene... pastel-colored illustration of a medieval England countryside town, set against the backdrop of a picturesque winter landscape. Cobblestone streets meander through the town, lined with charming beige-colored buildings that exude timeless charm and character. The clear blue sky above is graced with gracefully soaring little birds, creating a sense of harmony between nature and the human-made environment. The tranquil atmosphere is further enhanced by the absence of people, resulting in an idyllic, peaceful scene that transcends time and captures the essence of a bygone era. The overall effect of the illustration is a nostalgic and timeless depiction of a small town, nestled in the heart of a picturesque countryside.',
    },
    {
      path: '/carousel/a-serene-and-enchanting-pastel-colored-illustratio-rVsC5qlSSNCko2JdyP_F1w-N3Epz3wWQp6veoMrNRwb9A.png',
      label: 'Enchanting Landscape',
      text: 'Illustration of a medieval countryside town, nestled between rolling hills and picturesque landscapes. The cobblestone streets are lined with vividly colored, charming buildings, each exuding a timeless charm. The clear blue sky above is adorned with gracefully soaring birds, setting the stage for a perfect spring morning. The tranquil atmosphere is amplified by the absence of people, creating an idyllic, peaceful scene that transcends time and captures the essence of a bygone era.',
    },
    {
      path: '/carousel/dutch.png',
      label: 'Dutch Windmill',
      text: 'An enchanting illustration... of a medieval dutch countryside town, nestled between rolling hills and picturesque landscapes. The cobblestone streets are lined with vividly colored, charming buildings, each exuding a timeless charm. The clear blue sky above is adorned with gracefully soaring birds, setting the stage for a perfect spring morning. The tranquil atmosphere is amplified by the absence of people, creating an idyllic, peaceful scene that transcends time and captures the essence of a bygone era.',
    },
    {
      path: '/carousel/portugal.png',
      label: 'Portuguese Coast',
      text: 'A serene pastel-colored... illustration of a medieval Portuguese countryside town, nestled between rolling hills and picturesque landscapes. The cobblestone streets are lined with vividly colored, charming buildings, each exuding a timeless charm. The clear blue sky above is adorned with gracefully soaring birds, setting the stage for a perfect spring morning. The tranquil atmosphere is amplified by the absence of people, creating an idyllic, peaceful scene that transcends time and captures the essence of a bygone era.',
    },
    {
      path: '/carousel/spain.png',
      label: 'Spanish Village',
      text: 'A tranquil and picturesque... pastel-colored illustration of a quaint Spanish countryside medieval town. The town is nestled between rolling hills, featuring charming cobblestone streets and vividly colored buildings that exude a timeless charm. The clear blue sky above sets the stage for a perfect spring morning, with a few stray birds gracefully soaring through the air. The serene atmosphere is further accentuated by the absence of people, creating an idyllic and peaceful scene that transcends time.',
    },
  ];

  function nextImage() {
    currentIndex = (currentIndex + 1) % images.length;
  }

  function prevImage() {
    currentIndex = (currentIndex - 1 + images.length) % images.length;
  }
</script>

<div class="carousel">
  {#each images as image, index}
    <img
      src={image.path}
      alt={image.label}
      class={index === currentIndex ? 'fade' : ''}
    />
  {/each}
  <div class="image-label">
    <h3>{images[currentIndex].label}</h3>
    {#if images[currentIndex].text}
      <p>{images[currentIndex].text}</p>
    {/if}
  </div>
  <div class="carousel-buttons">
    <button class="carousel-button prev" on:click={prevImage}>
      <svg viewBox="0 0 24 24">
        <path d="M15.41 7.41L14 6l-6 6 6 6 1.41-1.41L10.83 12z" />
      </svg>
    </button>
    <button class="carousel-button next" on:click={nextImage}>
      <svg viewBox="0 0 24 24">
        <path d="M8.59 16.59L10 18l6-6-6-6-1.41 1.41L13.17 12z" />
      </svg>
    </button>
  </div>
</div>

<style>
  .carousel {
    position: relative;
    width: 100%;
    height: 100vh;
    overflow: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .carousel img {
    height: 100vh;
    object-fit: contain;
    position: absolute;
    left: 0;
    top: 0;
    opacity: 0;
    transition: opacity 0.5s ease;
  }

  .carousel img.fade {
    opacity: 1;
  }

  .image-label {
    position: absolute;
    bottom: 20px;
    right: 20px;
    background: rgba(0, 0, 0, 0.5);
    color: white;
    padding: 10px;
    width: 230px;
    height: 50px;
    overflow: auto;
    transition:
      width 0.3s ease,
      height 0.3s ease;
    z-index: 1;
  }

  .image-label:hover {
    width: 300px;
    height: 100px;
  }

  .carousel-buttons {
    position: absolute;
    top: 50%;
    width: 100%;
    display: flex;
    justify-content: space-between;
    transform: translateY(-50%);
    z-index: 1;
  }

  .carousel-button {
    background: transparent;
    color: white;
    border: none;
    cursor: pointer;
    z-index: 1;
    width: 40px;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
  }

  .prev {
    margin-left: 10px;
  }

  .next {
    margin-right: 10px;
  }
</style>
