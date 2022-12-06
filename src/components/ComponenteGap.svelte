<script>
  import SolteAqui from "./SolteAqui.svelte";
  export let id;
  export let solteAqui = false
</script>
<div id="{id}" class="relative h-1" data-type="gap">
  <div>
    <!---->
    <!---->{#if solteAqui}<SolteAqui />{/if}
    <!---->
    <!---->
    <!---->
  </div>
  <!---->
</div>