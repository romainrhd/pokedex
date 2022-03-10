<!-- TODO : Ajouter la notion de layout -->
<template>
  <div class="flex flex-col m-auto bg-red-600 border border-black rounded">
    <div class="flex m-auto space-x-1">
      <div class="bg-blue-500 p-4 m-2 rounded-3xl border-2"></div>
      <div class="flex space-x-1 pt-0.5 pl-2 mt-2">
        <div>
          <div class="bg-red-600 p-1 rounded-3xl border border-black"></div>
        </div>
        <div>
          <div class="bg-yellow-300 p-1 rounded-3xl border border-black"></div>
        </div>
        <div>
          <div class="bg-green-400 p-1 rounded-3xl border border-black"></div>
        </div>
      </div>
      <div class="px-16"></div>
    </div>
    <div class="flex flex-row">
      <div
        class="w-full border-t border-black h-10 bg-blue-500"
        id="trait"
      ></div>
    </div>
    <div class="h-80"></div>
  </div>
</template>
