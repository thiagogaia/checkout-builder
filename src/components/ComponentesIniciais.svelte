<script>
  import BotoesAdicionarLinha from "./BotoesAdicionarLinha.svelte";
import ComponenteArrasteAqui from "./ComponenteArrasteAqui.svelte";
    import ComponenteCheckout from "./ComponenteCheckout.svelte";


  import ComponenteGap from "./ComponenteGap.svelte";
    import ComponenteHeader from "./ComponenteHeader.svelte";
    import ContainerEmpty from "./ContainerEmpty.svelte";
  let solteAqui = false
</script>
<div class="flex relative border-2 border-transparent">
  <BotoesAdicionarLinha />
  <div class="w-full flex mx-auto p-2 max-w-960 flex-row">
    <div class="px-4" style="margin: 0px; width: 100%;">
      <div id="0,0" class="w-full relative h-full">
        <ComponenteGap id="0,0,0" solteAqui={solteAqui} />
        <ComponenteArrasteAqui />
      </div>
    </div>
  </div>
</div>
<div class="flex relative border-2 border-transparent">
  <BotoesAdicionarLinha />
  <div class="w-full flex mx-auto p-2 max-w-960 flex-row">
    <div class="px-4" style="margin: 0px auto; width: 70%;">
      <div id="1,0" class="w-full relative h-full">
        <ComponenteGap id="1,0,0"/>
        <ComponenteHeader />
        <ComponenteCheckout />
        <!---->
      </div>
    </div>
    <div class="px-4" style="margin: 0px auto; width: 30%;">
      <div id="1,1" class="w-full relative h-full">
        <ComponenteGap id="1,1,0" />
        <ComponenteArrasteAqui />
      </div>
    </div>
  </div>
</div>
<ContainerEmpty />