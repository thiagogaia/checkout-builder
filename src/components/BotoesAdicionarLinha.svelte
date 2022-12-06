<script>
  import BotoesHoverLinha from "./BotoesHoverLinha.svelte";
  export let handleHoverLinha = false
  export let handleHoverDuplicar = false
</script>
<div>
  <div>
    <div class="absolute z-50 top-0 flex justify-center items-center w-full -mt-8" class:displayNone={!handleHoverDuplicar}>
      <button class="bg-indigo-500 focus:outline-none bg-opacity-50 text-white px-10 hover:bg-opacity-100 cursor-pointer flex py-1 top-0">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-6 w-6">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path>
        </svg>
      </button>
    </div>
    <div class="absolute z-50 bottom-0 flex justify-center items-center w-full -mb-8" class:displayNone={!handleHoverDuplicar}>
      <button class="bg-indigo-500 focus:outline-none text-white bg-opacity-50 hover:bg-opacity-100 cursor-pointer px-10 flex py-1 top-0">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" class="h-6 w-6">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path>
        </svg>
      </button>
    </div>
  </div>
  <!---->
  <!---->
  <!---->
  {#if handleHoverLinha}
    <BotoesHoverLinha on:startDrag on:handleKeyDown />
  {/if}
  
</div>

<style>
  .displayNone {
    display: none;
  }
</style>