<script lang="ts">
    import soundSrc from "../public/img/sound.svg";
</script>

<div id="menu-popup">
    <button id="sound" class="no-btn"><img alt="Sound" src={soundSrc} /></button
    >
    <div id="grid">
        <div class="horiz">
            <h2>Easy 10%</h2>
        </div>
        <h2 id="easy-val">N</h2>
        <div class="horiz">
            <h2>Medium 15%</h2>
        </div>
        <h2 id="medium-val">N</h2>
        <div class="horiz">
            <h2>Hard 20%</h2>
        </div>
        <h2 id="hard-val">N</h2>
        <div class="horiz">
            <h2>Impossible 25%</h2>
        </div>
        <h2 id="impossible-val">N</h2>
    </div>
</div>

<style>
    #menu-popup {
        background-color: #aaa;
        position: absolute;
        width: 100%;
        height: 100%;
    }

    #sound {
        padding: 2px;
        border: 1px solid black;
        border-radius: 50%;
        background: none;
        cursor: pointer;
    }
    #sound img {
        width: 24px;
        height: 24px;
    }

    #grid {
        display: grid;
        grid-template-columns: 1fr 1fr;
        align-content: space-evenly;
        gap: 1rem;
    }
</style>
