<script lang="ts">
  import { onMount } from "svelte";
  import { MINES_NUMBER } from "./constants";
  import { GameController } from "./controller";
  import MenuPopup from "./MenuPopup.svelte";
  import { GameModel } from "./model";

  let show = false;

  onMount(() => {
    const canvas = document.getElementById("game");
    if (!(canvas instanceof HTMLCanvasElement))
      throw new Error("canvas is not a canvas");

    const model = new GameModel(MINES_NUMBER);
    new GameController(canvas, model);
  });
</script>

<div id="info-panel">
  <div class="element">
    <div class="img"></div>
    <span id="flags"></span>
  </div>
  <div class="element">
    <button
      id="start-btn"
      on:click={() => {
        show = !show;
      }}>Options</button
    >
  </div>
</div>
<div id="game-panel">
  <svelte:component this={show ? MenuPopup : null} />
  <canvas id="game">Your browser doesn't support canvas tag element</canvas>
</div>

<style>
  #info-panel {
    height: 40px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
  }

  #info-panel *:first-child {
    margin-left: auto;
  }

  .element {
    display: flex;
    gap: 4px;
  }

  .element .img {
    width: 30px;
    height: 30px;
    background-image: url(/img/mine.svg);
    background-size: 100% 100%;
  }

  #flags {
    font-size: 20px;
  }

  #start-btn {
    font-size: 16px;
    padding: 4px;
  }

  #game-panel {
    position: relative;
  }
</style>
