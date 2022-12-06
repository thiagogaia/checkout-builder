<script>
  import {
    dndzone, 
    SHADOW_ITEM_MARKER_PROPERTY_NAME, 
    SHADOW_PLACEHOLDER_ITEM_ID, 
    DRAGGED_ELEMENT_ID, 
    SOURCES, 
    TRIGGERS
  } from 'svelte-dnd-action';
  import {flip} from 'svelte/animate';
  export let displayAbaLinhas = false
  const flipDurationMs = 100;
  let items = [
    {
      id: 1,
      isLine: true,
      type: 'row', 
      rowColumnLayout: 1, 
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '100',
          styles: 'w-full',
          components: []
        }
      ]
    },
    {
      id: 2,
      isLine: true,
      type: 'row',
      rowColumnLayout: 2,
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '70',
          styles: 'w-9/12 mr-2',
          components: []
        },
        {
          id: 2,
          type: 'column', 
          width: '30',
          styles: 'w-3/12',
          components: []
        }
      ]
    },
    {
      id: 3,
      isLine: true,
      type: 'row',
      rowColumnLayout: 3,
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '30',
          styles: 'w-3/12 mr-2',
          components: []
        },
        {
          id: 2,
          type: 'column', 
          width: '70',
          styles: 'w-9/12',
          components: []
        }
      ]
    },
    {
      id: 4,
      isLine: true,
      type: 'row',
      rowColumnLayout: 4,
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '33.33',
          styles: 'w-4/12 mr-2',
          components: []
        },
        {
          id: 2,
          type: 'column', 
          width: '33.33',
          styles: 'w-4/12 mr-2',
          components: []
        },
        {
          id: 3,
          type: 'column', 
          width: '33.33',
          styles: 'w-4/12',
          components: []
        }
      ]
    },
  ]
  let dragDisabled = false
  let type = 'dragLines'
  function handleConsider(e) {
		items = e.detail.items;
	}

  function handleFinalize(e) {
    console.log('finalizou pela abaLinhas')
    items = e.detail.items;
	}
</script>
<div class="overflow-y-auto h-full pb-20 px-6" 
  class:displayNone={!displayAbaLinhas}
  use:dndzone={{items, dragDisabled, flipDurationMs, type}}
  on:consider={handleConsider} 
  on:finalize={handleFinalize}
  >
  {#each items as linha, key (linha.id)}
    <div animate:flip={{duration:flipDurationMs}}>
      <div class="bg-white rounded-md border cursor-pointer w-full mt-4 p-2 flex h-24">
        {#each linha.columns as column, keyColumn (column.id)}
          <div class="bg-gray-100 text-gray-300 {column.styles} 
            h-full flex justify-center items-center flex-col"
            >
            {keyColumn+1}
          </div>
        {/each}
      </div>
    </div>
  {/each}
    
</div>

<style>
  .displayNone {
    display: none;
  }
</style>