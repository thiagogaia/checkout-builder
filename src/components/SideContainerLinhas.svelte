<section aria-labelledby="slide-over-title" role="dialog" aria-modal="true" 
  class="fixed z-20 w-full top-0 pt-12 max-w-xs left-0 h-full" style="display: none;"
  >
  <div class="w-screen max-w-xs h-full">
    <div class="h-full flex flex-col bg-white border-l">
      <div class="px-6 bg-gray-50 py-4 border-b">
        <div class="flex items-start justify-between">
          <h2 id="slide-over-title" class="text-lg font-medium text-gray-900">
            Linha
          </h2>
          <div class="ml-3 h-7 flex items-center">
            <!---->
            <!---->
            <button class="rounded-md text-gray-400 hover:text-gray-500 focus:outline-none">
              <span class="sr-only">Close panel</span>
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true" class="h-5 w-5">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
              </svg>
            </button>
          </div>
        </div>
      </div>
      <div class="mt-6 relative flex-1 px-4 sm:px-6">
        <div>
          <label class="label">
            Colunas
          </label>
          <div class="grid grid-cols-2 gap-x-4 grid-flow-row">
            <div>
              <div class="bg-white rounded-md border cursor-pointer w-full mt-4 p-2 flex h-24">
                <div class="bg-gray-100 text-gray-300 w-full h-full flex justify-center items-center flex-col">1</div>
                <!---->
                <!---->
                <!---->
              </div>
            </div>
            <div>
              <div class="bg-white rounded-md border cursor-pointer w-full mt-4 p-2 flex h-24">
                <!---->
                <div class="bg-gray-100 text-gray-300 h-full w-9/12 mr-2 flex justify-center items-center flex-col">1</div>
                <div class="bg-gray-100 text-gray-300 h-full w-3/12 flex justify-center items-center flex-col">2</div>
                <!---->
                <!---->
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>