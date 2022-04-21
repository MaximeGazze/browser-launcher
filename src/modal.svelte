<script>
 export let show;
 export let title = '';
</script>

{#if show}
  <div class="modal" on:click={() => show = false}>
    <div class="modal-content" on:click|stopPropagation={_ => _} on:mousedown|stopPropagation={_ => _} on:mouseup|stopPropagation={_ => _}>
      <div class="modal-header">
        <div class="modal-title">{title}</div>
        <div class="close-button" on:click={() => show = false}>&times;</div>
      </div>
      <div class="modal-body">
        <slot />
      </div>
    </div>
  </div>
{/if}

<style>
 .modal {
   display: flex;
   justify-content: center;
   align-items: center;
   position: fixed;
   z-index: 100;
   left: 0;
   top: 0;
   width: 100%;
   height: 100%;
   /* overflow: auto; */
   background-color: rgba(4,4,4,0.4);
 }

 .modal-content {
   background-color: #221f2e;
   color: white;
   position: fixed;
   border-radius: 0.5rem;
   margin: 1rem;
   /* padding: 1rem; */
   border: 1px solid #2f2b3f;
   width: 90%;
   /* min-width: 800px; */
   max-width: 400px;
   /* box-shadow: 10px 10px 5px black; */
 }

 .modal-header {
   display: flex;
   flex-direction: row;
   justify-content: space-between;
   border-bottom: solid 1px #2f2b3f;
   padding: 0.5rem;
 }

 .modal-title {
   font-size: 2em;
   font-weight: bold;
   overflow: hidden;
   /* text-overflow: ellipsis; */
   /* white-space: nowrap; */
   padding: 0 0.75rem;
 }

 .modal-body {
   padding: 1rem;
 }

 .close-button {
   color: white;
   float: right;
   font-size: 2rem;
   padding: 0 10px;
   font-weight: bold;
   cursor: pointer;
 }

 .close-button:hover {
   color: black;
 }
</style>
