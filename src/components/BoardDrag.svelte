<script>
  import ComponenteArrasteAqui from "./ComponenteArrasteAqui.svelte";
  import ComponenteCheckout from "./ComponenteCheckout.svelte";
  import ComponenteGap from "./ComponenteGap.svelte";
  import ComponenteHeader from "./ComponenteHeader.svelte";
  import ContainerEmpty from "./ContainerEmpty.svelte";
  //velocidade
  //manutenção
  //qualidade do builder
  //documentação
  import {
    dndzone, 
    SHADOW_ITEM_MARKER_PROPERTY_NAME, 
    SHADOW_PLACEHOLDER_ITEM_ID, 
    DRAGGED_ELEMENT_ID, 
    SOURCES, 
    TRIGGERS
  } from 'svelte-dnd-action';
	import {flip} from 'svelte/animate';
    import ComponentesIniciais from "./ComponentesIniciais.svelte";
    import BotoesAdicionarLinha from "./BotoesAdicionarLinha.svelte";
	const flipDurationMs = 200;
  let dragDisabled = true;
  let items = [
		{
      id: 1, 
      type: 'row', 
      rowColumnLayout: 1, 
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '100', 
          components: []
        }
      ]
    },
		{
      id: 2, 
      type: 'checkout', 
      rowColumnLayout: 2, 
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '70', 
          components: [
            {
              id: 1,
              type: 'header',
              props: {
                color_background: "#247ef3ff",
                color_subtitle: "#000",
                color_title: "#000",
                font_size_subtitle: "14",
                font_size_title: "24",
                header_type: "bg_transparent",
                image_product: null,
                image_product_alignment: "left",
                image_top: null,
                product_image_type: "product",
                show_subtitle: false,
                subtitle: "Entrega digital instantânea após o pagamento.",
                title: "aaabaaa"
              }
            },
            {
              id: 2,
              type: 'checkout', 
              props: {}
            }
          ]
        },
        {
          id: 2,
          type: 'column', 
          width: '30', 
          components: []
        }
      ]
    },
    {
      id: 3, 
      type: 'row', 
      rowColumnLayout: 1, 
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '100', 
          components: []
        }
      ]
    },
    {
      id: 4, 
      type: 'row', 
      rowColumnLayout: 1, 
      columns: [
        {
          id: 1,
          type: 'column', 
          width: '33.33', 
          components: []
        },
        {
          id: 2,
          type: 'column', 
          width: '33.33', 
          components: []
        },
        {
          id: 3,
          type: 'column', 
          width: '33.33', 
          components: []
        }
      ]
    },
	];

  function copyComponent(id, items) {
    console.warn(`copying ${id}`);
    const idx = items.findIndex(item => item.id === id);
    const newId = `${id}_copy_${Math.round(Math.random()*100000)}`;
    let coyA = items.splice(idx, 0, {...items[idx], id: newId});
    console.log(coyA)
  }
  function handleConsider(e) {
    const {items: newItems, info: {source, trigger, id}} = e.detail;
    if (trigger === TRIGGERS.DRAG_STARTED) {
      // e.detail.items = copyComponent(id, items)
    }
		items = e.detail.items;
    // Ensure dragging is stopped on drag finish via keyboard
		if (source === SOURCES.KEYBOARD && trigger === TRIGGERS.DRAG_STOPPED) {
			dragDisabled = true;
		}
	}

  function handleFinalize(e) {
    const {items: newItems, info: {source}} = e.detail;
    console.log('finalizou pelo board', newItems)

		items = e.detail.items;
    //habilitar o draganddrop pelo botão superior do hover
    if (source === SOURCES.POINTER) {
			dragDisabled = true;
		}
	}
  let type = 'dragLines'
  let solteAqui = false
  let hoverItem = false

  let dataHoverLinha = {}
  function handleMouseEnterComponent(item) {
    dataHoverLinha.mouEnter = item.id
    // console.log(dataHoverLinha)
  }

  function startDrag(e) {
		// preventing default to prevent lag on touch devices (because of the browser checking for screen scrolling)
		e.preventDefault();
		dragDisabled = false;
	}

	function handleKeyDown(e) {
		if ((e.key === "Enter" || e.key === " ") && dragDisabled) dragDisabled = false;
	}
</script>
<div class="h-full max-h-screen w-full overflow-y-auto fixed left-0 pl-[330px]">
  <div class="px-6 py-4 relative mt-16" style="background-color: rgb(246, 246, 246);">
    <div class="flex-col flex z-10 relative"
      style="min-height: 100px; background-color: rgb(239, 241, 243); 
      font-family: 'Open Sans'; background-position: center top; 
      background-image: url('null'); background-repeat: no-repeat;"
      use:dndzone={{items, dragDisabled, flipDurationMs, type}} 
      on:consider={handleConsider} 
      on:finalize={handleFinalize}
    >
      {#each items as item, key (item.id)}
        <div class="flex relative border-2 border-transparent"
          
          animate:flip={{duration:flipDurationMs}}
          on:mouseover={() => handleMouseEnterComponent(item)}
          on:focus={() => console.log('')}
          >
          <BotoesAdicionarLinha 
            handleHoverLinha={dataHoverLinha.mouEnter == item.id ? true : false}
            on:startDrag={startDrag} on:handleKeyDown={handleKeyDown}
            />
          <div class="w-full flex mx-auto p-2 max-w-960 flex-row">
            {#each item.columns as column, keyColumn (column.id)}
              <div class="px-4" style="margin: 0px; width: {column.width}%;">
                <div id="{key +','+keyColumn}" class="w-full relative h-full">
                  {#if (Array.isArray(column.components) && column.components.length)}
                    {#each column.components as componet, keyComponent (componet.id)}
                      {#if (componet.type == 'header')}
                        <ComponenteHeader />
                      {:else if (componet.type == 'checkout')}
                        <ComponenteCheckout />
                      {/if}
                    {/each}
                  {:else}
                    <ComponenteGap id="{key +','+keyColumn},0" solteAqui={solteAqui} />
                    <ComponenteArrasteAqui />
                  {/if}
                </div>
                 
              </div>
            {/each}
          </div>	
        </div>
      {/each}
    </div>
  </div>
</div>