<script>
  let solteAqui = false
  function dragEnter() {
    // solteAqui = true
    console.log('entrou do nada: ')
  }

  function dragLeave() {
    solteAqui = false
    console.log('saiu do nada: ')
  }

  function dragOver() {
    solteAqui = true
    console.log('to aqui hein')
  }

  function dropIn() {
    console.log('dropou mano')
  }
</script>
<div class="flex relative border-2 border-transparent"
  on:dragenter={dragEnter} 
  on:dragleave={dragLeave} 
  on:dragover={dragOver}
  on:drop={dropIn}
  >
  <div>
    <!---->
    <!---->
    <!---->
    <!---->
    <!---->
  </div>
  <div class="w-full flex mx-auto p-2 max-w-960 flex-row">
    
  </div>
</div>