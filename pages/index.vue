<template>
  <div id="index" class="flex flex-col h-full w-full">
    <div id="container" class="pt-24 h-auto flex-grow w-full flex flex-row">
      <div id="text-area" class="w-1/3 h-full px-10 py-24">
        <h1 class="text-5xl ninja-font text-gray-900"> Hrrs01's Google Dojo</h1>
        <h1 class="text-3xl ninja-font text-gray-800 pt-5"><span class="text-5xl">W</span>elcome to my dojo.
          This is where i refine my googling skills. <br>
          <span class="text-5xl">F</span>eel free to practice your Googling skills here, or get an insight into some of my projects.
          <br><br>
          <span class="text-lg">(Google's im feeling lucky redirect is buggy. Enjoy feeling ducky)</span>
        </h1>
      </div>
      <div id="google-area" class="w-2/3 h-full pr-24 py-24">
        <div id="google-container" class="h-full w-full rounded-lg px-5 py-5 shadow-2xl bg-ninja-gray">
          <div class="bg-white h-full w-full rounded-lg border-2 border-blue-200 flex flex-col items-center justify-center">
            <img class="" src="@/assets/img/googlelogo.png"  />
            <input class="border border-gray-400 rounded-full mt-8 w-1/2 bg-gray-100 text-gray-600 hover:shadow-md focus:outline-none px-5" v-on:keydown.enter="googleThat" style="height:2.75rem" type="text" id="google-search" name="search" />
            <div class="pt-4">
            <button class=" mt-4 py-2 px-3 bg-ninja-button text-gray-600 rounded-md mr-1 border border-gray-100 hover:border-gray-300 " @click="googleThat">Google Search </button>
            <button class=" mt-4 py-2 px-3 bg-ninja-button text-gray-600 rounded-md ml-1 border border-gray-100 hover:border-gray-300" @click="googleThat(true)"> I'm Feeling Ducky</button>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  methods: {
    googleThat: (imfl = false) => {
      if(imfl)
        window.location.replace("https://duckduckgo.com/?q=!ducky+"+encodeURI(document.getElementById("google-search").value))
      else
       window.location.replace("https://google.com/search?q="+encodeURI(document.getElementById("google-search").value))
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Shadows+Into+Light&display=swap');

.ninja-font {
  font-family: "Shadows Into Light", sans-serif;

}
</style>
