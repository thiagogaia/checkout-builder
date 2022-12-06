<script>
  export let displayAbaConfiguracoes = false
</script>
<div class="bg-white w-full h-full" class:displayNone={!displayAbaConfiguracoes} >
  <div class="h-full w-full px-4 pt-4 pb-20 overflow-y-auto">
    <div class="w-40">
      <div>
        <label class="block text-sm font-medium leading-5 text-gray-700 mb-1"> Font Family </label>
        <select
          class="form-select shadow-sm block w-full pl-3 pr-10 py-2 text-base leading-6 border-gray-300 focus:outline-none focus:shadow-outline-blue focus:border-blue-300 sm:text-sm sm:leading-5 transition ease-in-out duration-150"
        >
          <option value="Open Sans">
            Open Sans
          </option>
          <option value="Roboto">
            Roboto
          </option>
        </select>
      </div>
    </div>
    <div class="mt-6">
      <div class="flex items-center">
        <div>
          <label class="label mb-1">Cor de fundo</label>
          <div>
            <div class="relative inline-block">
              <div >
                <span class="rounded-md block shadow-sm relative dropdown-trigger">
                  <button id="options-menu" class="w-20 rounded-md h-4 border border-gray-300 p-4 transition ease-in-out duration-150" style="background: rgb(239, 241, 243);"></button>
                </span>
              </div>
              <div class="dropdown z-500">
                <div class="w-60 z-500 rounded-md shadow-lg" style="display: none;">
                  <div class="vacp-color-picker" style="--vacp-hsl-h: 0.583333; --vacp-hsl-s: 0.142857; --vacp-hsl-l: 0.945098; --vacp-hsl-a: 1;">
                    <div
                      class="vacp-color-space"
                      style="
                        position: relative;
                        background-color: hsl(calc(var(--vacp-hsl-h) * 360) 100% 50%);
                        background-image: linear-gradient(to top, rgb(0, 0, 0), transparent), linear-gradient(to right, rgb(255, 255, 255), transparent);
                      "
                    >
                      <div tabindex="0" aria-label="Color space thumb" class="vacp-color-space-thumb" style="box-sizing: border-box; position: absolute; left: 1.64609%; bottom: 95.2941%;"></div>
                    </div>
                    <label for="color-picker-4d39924e-50b3-4a64-9e69-c37edbec6983-hue-slider" class="vacp-range-input-label vacp-range-input-label--hue">
                      <span class="vacp-range-input-label-text vacp-range-input-label-text--hue"><span class="sr-only">Hue</span></span>
                      <input id="color-picker-4d39924e-50b3-4a64-9e69-c37edbec6983-hue-slider" type="range" min="0" max="360" step="1" class="vacp-range-input vacp-range-input--hue" />
                    </label>
                    <label for="color-picker-4d39924e-50b3-4a64-9e69-c37edbec6983-alpha-slider" class="vacp-range-input-label vacp-range-input-label--alpha">
                      <span class="vacp-range-input-label-text vacp-range-input-label-text--alpha"><span class="sr-only">Alpha</span></span>
                      <input id="color-picker-4d39924e-50b3-4a64-9e69-c37edbec6983-alpha-slider" type="range" min="0" max="100" step="1" class="vacp-range-input vacp-range-input--alpha" />
                    </label>
                    <button type="button" class="vacp-copy-button">
                      <span class="sr-only">Copy color</span>
                      <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="15" height="15" viewBox="0 0 15 15">
                        <path d="M5 0v2H1v13h12v-3h-1v2H2V5h10v3h1V2H9V0zm1 1h2v2h3v1H3V3h3z" fill="currentColor"></path>
                        <path d="M10 7v2h5v2h-5v2l-3-3zM3 6h5v1H3zm0 2h3v1H3zm0 2h3v1H3zm0 2h5v1H3z" fill="currentColor"></path>
                      </svg>
                    </button>
                    <div class="vacp-color-inputs" style="width: 100%;">
                      <div class="vacp-color-input-group">
                        <label for="color-picker-4d39924e-50b3-4a64-9e69-c37edbec6983-color-hex" class="vacp-color-input-label" style="width: 140px;">
                          <input id="color-picker-4d39924e-50b3-4a64-9e69-c37edbec6983-color-hex" type="text" class="vacp-color-input" />
                        </label>
                      </div>
                      <div class="vacp-color-input-group">
                        <label class="vacp-color-input-label">
                          <input type="number" min="0" max="100" class="vacp-color-input" style="width: 52px;" />
                          &nbsp;%
                        </label>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="mt-6">
      <label class="label mb-1">Imagem de fundo</label>
      <div>
        <div>
          <div class="fixed bottom-0 inset-x-0 px-4 pb-4 sm:inset-0 sm:flex sm:items-center sm:justify-center" style="z-index: 5000; display: none;">
            <div class="fixed inset-0 transition-opacity"><div class="absolute inset-0 bg-gray-500 opacity-75"></div></div>
            <div role="dialog" aria-modal="true" aria-labelledby="modal-headline" class="bg-white overflow-hidden rounded-lg shadow-xl transform transition-all sm:w-full sm:max-w-3xl">
              <div class="bg-white px-4 pt-5 pb-4 sm:p-6">
                <div>
                  <div class="mt-3 sm:mt-0 sm:ml-4 sm:text-left">
                    <h3 id="modal-headline" class="text-lg leading-6 font-medium text-gray-900">
                      Recortar &amp; Gerenciar
                    </h3>
                    <!---->
                    <div class="mt-2">
                      <div>
                        <div class=""><img alt="" class="block" style="width: 1200px; height: 400px;" /></div>
                        <div class="w-48 mt-4">
                          <div>
                            <label class="block text-sm font-medium leading-5 text-gray-700 mb-1"> Type </label>
                            <select
                              class="form-select shadow-sm block w-full pl-3 pr-10 py-2 text-base leading-6 border-gray-300 focus:outline-none focus:shadow-outline-blue focus:border-blue-300 sm:text-sm sm:leading-5 transition ease-in-out duration-150"
                            >
                              <option value="free">
                                Personalizado
                              </option>
                              <option value="square">
                                Quadrado
                              </option>
                              <option value="circle">
                                Círculo
                              </option>
                              <option value="portrait">
                                Retrato
                              </option>
                              <option value="landscape">
                                Paisagem
                              </option>
                            </select>
                          </div>
                        </div>
                        <div class="flex h-full flex-col w-full absolute top-0 py-10" style="display: none;">
                          <div class="bg-gray-500 mt-1 h-80 w-full mb-4 skeleton-box"></div>
                          <div class="flex items-center justify-between border-gray-200">
                            <div class="flex-1"><div class="bg-gray-500 mt-1 h-12 w-full skeleton-box"></div></div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="bg-gray-50 px-4 py-3 sm:px-6 sm:flex sm:flex-row-reverse">
                <span class="flex w-full rounded-md shadow-sm sm:ml-3 sm:w-auto">
                  <button
                    type="button"
                    class="cursor-pointer inline-flex justify-center w-full rounded-md border border-transparent px-4 py-2 text-base leading-6 font-medium text-white shadow-sm focus:outline-none focus:border-red-700 transition ease-in-out duration-150 sm:text-sm sm:leading-5 bg-indigo-600 hover:bg-indigo-500 focus:shadow-outline-indigo"
                  >
                    <!---->
                    Salvar corte
                  </button>
                </span>
                <span class="mt-3 flex w-full rounded-md shadow-sm sm:mt-0 sm:w-auto">
                  <button
                    type="button"
                    class="cursor-pointer inline-flex justify-center w-full rounded-md border border-gray-300 px-4 py-2 bg-white text-base leading-6 font-medium text-gray-700 shadow-sm hover:text-gray-500 focus:outline-none focus:border-blue-300 focus:shadow-outline-blue transition ease-in-out duration-150 sm:text-sm sm:leading-5"
                  >
                    Cancelar
                  </button>
                </span>
              </div>
            </div>
          </div>
        </div>
        <label
          for="file-dd6be782-b8c1-43e4-9291-f6f5d90cdf45"
          id="filedd6be782-b8c1-43e4-9291-f6f5d90cdf45"
          class="hover:bg-gray-50 cursor-pointer flex justify-center px-6 pt-5 pb-6 border-2 border-gray-300 transition duration-300 border-dashed rounded-md h-48 items-center max-w-lg"
        >
          <div class="space-y-1 text-center">
            <svg stroke="currentColor" fill="none" viewBox="0 0 48 48" aria-hidden="true" class="mx-auto h-12 w-12 text-gray-400">
              <path
                d="M28 8H12a4 4 0 00-4 4v20m32-12v8m0 0v8a4 4 0 01-4 4H12a4 4 0 01-4-4v-4m32-4l-3.172-3.172a4 4 0 00-5.656 0L28 28M8 32l9.172-9.172a4 4 0 015.656 0L28 28m0 0l4 4m4-24h8m-4-4v8m-12 4h.02"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
              ></path>
            </svg>
            <div class="flex flex-col text-sm text-gray-600">
              <div class="relative cursor-pointe rounded-md font-medium text-indigo-600 hover:text-indigo-500 focus-within:outline-none focus-within:ring-2 focus-within:ring-offset-2 focus-within:ring-indigo-500">
                <span>Selecione do computador</span> <input id="file-dd6be782-b8c1-43e4-9291-f6f5d90cdf45" accept="image/jpeg,image/jpg,image/png" name="filedd6be782-b8c1-43e4-9291-f6f5d90cdf45" type="file" class="sr-only" />
              </div>
              <p class="pl-1">ou arraste aqui</p>
            </div>
            <p class="text-xs text-gray-500">
              PNG, JPG até 10 MB
            </p>
          </div>
        </label>
      </div>
    </div>
    <div class="mt-6">
      <label class="flex items-center mt-4">
        <input type="checkbox" class="form-checkbox h-4 w-4 text-indigo-600 transition duration-150 ease-in-out" />
        <span class="block font-medium leading-5 text-gray-700 ml-2 cursor-pointer">Fixar imagem de fundo ao descer a tela</span>
      </label>
      <label class="flex items-center mt-4">
        <input type="checkbox" class="form-checkbox h-4 w-4 text-indigo-600 transition duration-150 ease-in-out" /> <span class="block font-medium leading-5 text-gray-700 ml-2 cursor-pointer">Repetir imagem de fundo</span>
      </label>
      <label class="flex items-center mt-4">
        <input type="checkbox" class="form-checkbox h-4 w-4 text-indigo-600 transition duration-150 ease-in-out" /> <span class="block font-medium leading-5 text-gray-700 ml-2 cursor-pointer">Expandir / cobrir fundo</span>
      </label>
    </div>
  </div>
</div>
<style>
  .displayNone {
    display: none;
  }
</style>