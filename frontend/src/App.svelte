<script>
  import  Navbar from "./Navbar.svelte";
  import { Greet } from "../wailsjs/go/main/App.js";

  let selectedKeybind = null;
  function selectKeybind(keybind) {
    selectedKeybind = keybind;
  }

  // Javascript has no structs right?
  class Keybind {
    constructor(key, quickcast, indicator) {
      this.key = key;
      this.quickcast = quickcast;
      this.indicator = indicator;
    }
  }

  let keybinds = [
    new Keybind("Q", true, false),
    new Keybind("W", true, false),
    new Keybind("E", true, true),
    new Keybind("R", false, false),
  ];
</script>

<main>
  <Navbar />
  <div class="pt-[3%] flex flex-col space-y-4 justify-center p-4 ml-52">
    {#each keybinds as keybind (keybind)}
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div class="keybind w-[200px] h-[120px] p-4 rounded-md shadow-xl select-none {selectedKeybind === keybind ? 'active' : ''}" on:click="{() => selectKeybind(keybind)}">
        <div class="font-semibold text-4xl">{keybind.key}</div>
        <div>{keybind.quickcast ? "Quick cast" : "Normal cast"}</div>
        <div>{keybind.indicator ? "Indicator" : "No Indicator"}</div>
      </div>
    {/each}
  </div>
</main>

<style>
  .keybind {
    border: 2px solid var(--accent-100);
    background-color: var(--bg-base-100);
    color: var(--text-100);
  }

  .keybind.active {
    background-color: var(--accent-100);
  }

  .keybind:hover {
    cursor: pointer;
  }
</style>
