<script lang="ts">
    import { onMount } from "svelte";
    import dialog from "$lib/dialog.json";

    var i = 0;
    var currentId = 0;
    const speed = 50;

    function typewriter() {
        const txt = dialog[currentId].text;
        if(i < txt.length) {
            document.getElementById("dialog-box").innerHTML += txt.charAt(i);
            i++;
            setTimeout(typewriter, speed);
        }
    }

    onMount(() => {
        typewriter();
    })

    function nextLine() {
        i = 0;
        currentId++;
        document.getElementById("dialog-box").innerHTML = "";
        typewriter();
    }
</script>

<button id="dialog-box" onclick={nextLine} aria-label="reactive text" class="w-full cursor-default p-2 text-left bg-[#004E6E] border-2 border-[#FDFCFD] ring-1 ring-black font-sans italic text-2xl text-white text-shadow">

</button>

<style>
    .text-shadow {
        text-shadow: 2px 2px 0 black;
    }
</style>