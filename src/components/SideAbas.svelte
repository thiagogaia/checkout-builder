<script>
  import { createEventDispatcher } from 'svelte';
  const dispatch = createEventDispatcher()

  let tabComponentes = true
  let tabLinhas = false
  let tabConfiguracoes = false
  function changeTabs(comp) {
    console.log(comp, 'dentro do SideAbas')
    dispatch('changeTabs', {
			component: comp
		});

    if (comp == 'tabComponentes') {
      tabComponentes = true
      tabLinhas = false
      tabConfiguracoes = false
    }

    if (comp == 'tabLinhas') {
      tabComponentes = false
      tabLinhas = true
      tabConfiguracoes = false
    }

    if (comp == 'tabConfiguracoes') {
      tabComponentes = false
      tabLinhas = false
      tabConfiguracoes = true
    }
  }
</script>
<div>
  <div class="block">
    <nav aria-label="Tabs" class="relative z-0 rounded-lg shadow flex divide-x divide-gray-200">
      <div class="rounded-l-lg group relative min-w-0 cursor-pointer flex-1 
        overflow-hidden bg-white py-4 px-4 text-xs font-medium text-center 
        hover:bg-gray-50 focus:z-10" 
        class:ext-gray-900={tabComponentes}
        class:text-gray-500={!tabComponentes}
        class:hover:text-gray-700={!tabComponentes}
        on:click={() => changeTabs('tabComponentes')}
        on:keypress={() => console.log('seilah')}
        >
        <span>
          Componentes
        </span>
        <span aria-hidden="true" class="absolute inset-x-0 bottom-0 h-0.5" 
          class:bg-indigo-500={tabComponentes}
          class:bg-transparent={!tabComponentes}
        ></span>
      </div>
      <div class="rounded-l-lg group relative min-w-0 cursor-pointer flex-1 
        overflow-hidden bg-white py-4 px-4 text-xs font-medium text-center 
        hover:bg-gray-50 focus:z-10 text-gray-500 hover:text-gray-700"
        class:ext-gray-900={tabLinhas}
        class:text-gray-500={!tabLinhas}
        class:hover:text-gray-700={!tabLinhas} 
        on:click={() => changeTabs('tabLinhas')}
        on:keypress={() => console.log('seilah')}
        >
        <span>
          Linhas
        </span>
        <span aria-hidden="true" class="absolute inset-x-0 bottom-0 h-0.5"
          class:bg-indigo-500={tabLinhas}
          class:bg-transparent={!tabLinhas}
          ></span>
      </div>
      <div class="rounded-l-lg group relative min-w-0 cursor-pointer flex-1 
        overflow-hidden bg-white py-4 px-4 text-xs font-medium text-center 
        hover:bg-gray-50 focus:z-10 text-gray-500 hover:text-gray-700" 
        class:ext-gray-900={tabConfiguracoes}
        class:text-gray-500={!tabConfiguracoes}
        class:hover:text-gray-700={!tabConfiguracoes} 
        on:click={() => changeTabs('tabConfiguracoes')}
        on:keypress={() => console.log('seilah')}
        >
        <span>
          Configurações
        </span>
        <span aria-hidden="true" class="absolute inset-x-0 bottom-0 h-0.5"
          class:bg-indigo-500={tabConfiguracoes}
          class:bg-transparent={!tabConfiguracoes}
          ></span>
      </div>
    </nav>
  </div>
</div>