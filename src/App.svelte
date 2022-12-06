<script>
  import AbaComponentes from "./components/AbaComponentes.svelte";
  import AbaConfiguracoes from "./components/AbaConfiguracoes.svelte";
  import AbaLinhas from "./components/AbaLinhas.svelte";
  import BoardDrag from "./components/BoardDrag.svelte";
    import DragHost from "./components/dragHost.svelte";
  import Header from "./components/Header.svelte";
  import SideAbas from "./components/SideAbas.svelte";

  let tabComponentes = true
  let tabLinhas = false
  let tabConfiguracoes  = false
  function handleChangeTabs(event) {
    console.log(event.detail.component, 'evento dentro do App')
    if (event.detail.component == 'tabComponentes') {
      tabComponentes = true
      tabLinhas = false
      tabConfiguracoes  = false
    }

    if (event.detail.component == 'tabLinhas') {
      tabComponentes = false
      tabLinhas = true
      tabConfiguracoes  = false
    }

    if (event.detail.component == 'tabConfiguracoes') {
      tabComponentes = false
      tabLinhas = false
      tabConfiguracoes  = true
    }
  }
</script>
<div class="w-full min-h-screen flex">
  <div data-v-285f8f78="" class="flash--wrapper">
    <span data-v-285f8f78=""></span>
  </div>
  <div><!----></div>
  <!-- DragHost |Colocar caso seja necessário|-->
  <div class="w-full">
    <Header />
    <BoardDrag />
  </div>
  <div class="w-full max-w-xs pt-16"></div><!-- para dar um padding top e encaixar no layout-->
  <div class="pt-16">
    <!-- SideContainerLinhas -->
    <!-- SideContainerConfigs -->
  </div>
  <div class="bg-gray-50 border-l w-full max-w-xs fixed z-10 right-0 h-screen pt-16">
    <SideAbas on:changeTabs={handleChangeTabs} />
    <!-- ABA componentes-->
    <AbaComponentes displayAbaComponentes={tabComponentes} />
    <!-- ABA Linhas-->
    <AbaLinhas displayAbaLinhas={tabLinhas} />
    <!-- ABA configurações-->
    <AbaConfiguracoes displayAbaConfiguracoes={tabConfiguracoes} />
  </div>
  <!---->
</div>
