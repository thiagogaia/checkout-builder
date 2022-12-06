<script>
    import HeraderBotoes from "./HeraderBotoes.svelte";

</script>
<div class="px-10 py-1 fixed z-30 bg-gray-50 top-0 border-b flex justify-between items-center w-full">
  <div class="flex items-center">
    <div class="text-2xl mr-4">
      <div>
        <!---->
        <input
          type="text"
          autocomplete="off"
          name="null"
          value="DO NADA"
          class="form-input block py-2 px-3 border border-gray-300 rounded-md 
          shadow-sm focus:outline-none focus:shadow-outline-blue 
          focus:border-blue-300 transition duration-150 ease-in-out 
          sm:text-sm sm:leading-5 text-xl sm:text-xl"
        />
        <!---->
      </div>
    </div>
    <div class="flex items-center">
      <div class="p-2 rounded-full cursor-pointer bg-indigo-50 text-indigo-800 border border-indigo-200">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" width="24px" height="24px">
          <path fill-rule="evenodd" d="M3 5a2 2 0 012-2h10a2 2 0 012 2v8a2 2 0 01-2 2h-2.22l.123.489.804.804A1 1 0 0113 18H7a1 1 0 01-.707-1.707l.804-.804L7.22 15H5a2 2 0 01-2-2V5zm5.771 7H5V5h10v7H8.771z" clip-rule="evenodd"></path>
        </svg>
      </div>
      <div class="p-2 rounded-full ml-4 cursor-pointer bg-white border hover:bg-gray-50 transition">
        <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" width="24px" height="24px">
          <path fill-rule="evenodd" d="M7 2a2 2 0 00-2 2v12a2 2 0 002 2h6a2 2 0 002-2V4a2 2 0 00-2-2H7zm3 14a1 1 0 100-2 1 1 0 000 2z" clip-rule="evenodd"></path>
        </svg>
      </div>
      <!---->
    </div>
  </div>
  <!-- <HeraderBotoes /> -->
</div>