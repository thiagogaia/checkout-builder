<script>
  import Others from "./Others.svelte";
  export let displayAbaComponentes = true

  function dragComponent(id) {
    let componentText = document.getElementById(id)
    // console.log(id)
    componentText.setAttribute('draggable', 'true')
  }

  function dragStart(id) {
    // console.log('inciou o arrastar')
  }

  function dragging(id) {
    // console.log('ta arrastando')
  }

  function dragEnd(id) {
    console.log('terminou de arrastar do nada')
    let componentText = document.getElementById(id)
    componentText.setAttribute('draggable', 'false')
  }
</script>
<div class="overflow-y-auto h-full pb-20" class:displayNone={!displayAbaComponentes}>
  <div class="px-2 mt-4">
    <div class="text-gray-500 text-center text-sm uppercase">Componentes</div>
  </div>
  <div class="grid grid-cols-2 gap-2 py-4 px-2">
    <div id="component_drag_text" 
      on:mousedown={() => dragComponent('component_drag_text')} 
      on:dragstart={() => dragStart('component_drag_text')}
      on:drag={() => dragging('component_drag_text')}
      on:dragend={() => dragEnd('component_drag_text')}
      >
      <div class="cursor-pointer relative transform w-full bg-white text-center p-2 text-sm border text-gray-900 transition duration-200">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" width="24px" height="24px" class="text-gray-500 mx-auto">
          <path fill-rule="evenodd" d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h6a1 1 0 110 2H4a1 1 0 01-1-1z" clip-rule="evenodd"></path>
        </svg>
        <div class="capitalize mt-2">Texto</div>
      </div>
    </div>
    
    <!--Others -->
    <Others />
  </div>
  <!-- Extras-->
</div>

<style>
  .displayNone {
    display: none;
  }
</style>