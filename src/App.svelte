<script>
 import Modal from './modal.svelte';
 const menuitem = [
   { title: 'youtube', icon: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><!-- Font Awesome Pro 5.15.4 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) --><path d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"/></svg>', href: 'https://www.youtube.com' },
   { title: 'reddit', icon: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><!-- Font Awesome Pro 5.15.4 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) --><path d="M201.5 305.5c-13.8 0-24.9-11.1-24.9-24.6 0-13.8 11.1-24.9 24.9-24.9 13.6 0 24.6 11.1 24.6 24.9 0 13.6-11.1 24.6-24.6 24.6zM504 256c0 137-111 248-248 248S8 393 8 256 119 8 256 8s248 111 248 248zm-132.3-41.2c-9.4 0-17.7 3.9-23.8 10-22.4-15.5-52.6-25.5-86.1-26.6l17.4-78.3 55.4 12.5c0 13.6 11.1 24.6 24.6 24.6 13.8 0 24.9-11.3 24.9-24.9s-11.1-24.9-24.9-24.9c-9.7 0-18 5.8-22.1 13.8l-61.2-13.6c-3-.8-6.1 1.4-6.9 4.4l-19.1 86.4c-33.2 1.4-63.1 11.3-85.5 26.8-6.1-6.4-14.7-10.2-24.1-10.2-34.9 0-46.3 46.9-14.4 62.8-1.1 5-1.7 10.2-1.7 15.5 0 52.6 59.2 95.2 132 95.2 73.1 0 132.3-42.6 132.3-95.2 0-5.3-.6-10.8-1.9-15.8 31.3-16 19.8-62.5-14.9-62.5zM302.8 331c-18.2 18.2-76.1 17.9-93.6 0-2.2-2.2-6.1-2.2-8.3 0-2.5 2.5-2.5 6.4 0 8.6 22.8 22.8 87.3 22.8 110.2 0 2.5-2.2 2.5-6.1 0-8.6-2.2-2.2-6.1-2.2-8.3 0zm7.7-75c-13.6 0-24.6 11.1-24.6 24.9 0 13.6 11.1 24.6 24.6 24.6 13.8 0 24.9-11.1 24.9-24.6 0-13.8-11-24.9-24.9-24.9z"/></svg>', href: 'https://www.reddit.com' },
   { title: 'student portal', icon: '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><!-- Font Awesome Pro 5.15.4 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) --><path d="M622.34 153.2L343.4 67.5c-15.2-4.67-31.6-4.67-46.79 0L17.66 153.2c-23.54 7.23-23.54 38.36 0 45.59l48.63 14.94c-10.67 13.19-17.23 29.28-17.88 46.9C38.78 266.15 32 276.11 32 288c0 10.78 5.68 19.85 13.86 25.65L20.33 428.53C18.11 438.52 25.71 448 35.94 448h56.11c10.24 0 17.84-9.48 15.62-19.47L82.14 313.65C90.32 307.85 96 298.78 96 288c0-11.57-6.47-21.25-15.66-26.87.76-15.02 8.44-28.3 20.69-36.72L296.6 284.5c9.06 2.78 26.44 6.25 46.79 0l278.95-85.7c23.55-7.24 23.55-38.36 0-45.6zM352.79 315.09c-28.53 8.76-52.84 3.92-65.59 0l-145.02-44.55L128 384c0 35.35 85.96 64 192 64s192-28.65 192-64l-14.18-113.47-145.03 44.56z"/></svg>', href: 'https://portailetudiant.uqam.ca/' },
 ];
</script>

<svelte:head>
  <title>Launcher</title>
  <script src="https://kit.fontawesome.com/7ff7a3cf50.js" crossorigin="anonymous"></script>
</svelte:head>

<main>
  <img class="background" src="background.gif" alt="background" />
  <div class="menu">
    {#each menuitem as item}
      <a href="{item.href}" class="menu-item">
        {@html item.icon}
      </a>
    {/each}
  </div>

  <Modal show="" title="New bookmark">
    <form>
      <label for="title">Title</label>
      <input name="title" type="text" placeholder="title" />
      <label for="title">Icon</label>
      <input name="icon" type="text" placeholder="icon" />
      <label for="url">Url</label>
      <input name="url" type="text" placeholder="url" />
    </form>
  </Modal>
</main>

<style>
 :root {
   --color-white: #f2f4f3;
   --color-light-grey: #cad4de;
   --color-grey: #6c8091;
   --color-dark-grey: #3f495b;
   --color-secondary: #5c5f82;
   --color-primary: #f1a5a0;
   --color-accent: #efb8cc;

   --menu-width: 100px;
   --rounded: 10px;
 }

 .background {
   position: absolute;
   bottom: 0;
   height: 100%;
   width: 100%;
   z-index: -1;
   object-fit: cover;
 }

 .menu {
   display: flex;
   position: fixed;
   flex-direction: column;
   background-color: rgba(202, 212, 222, 0.7);
   border-radius: var(--rounded);
   width: var(--menu-width);
   top: 0;
   bottom: 0;
   margin: 10px;
   overflow-y: scroll;

   -ms-overflow-style: none;
   scrollbar-width: none;
 }

 .menu::-webkit-scrollbar {
   display: none;
 }

 .menu-item {
   justify-content: center;
   aspect-ratio: 1 / 1;
   padding: 10px;
   /* background-color: rgba(63, 73, 91, 1); */
 }

 .menu-item::hover {
   background-color: rgba(63, 73, 91, 1);
 }

</style>
