<script>
    import ContMod, {tot} from "./ContMod.svelte";

</script>
<button on:click={()=>alert(tot())}>Click for Total Value</button>
<hr>
<ContMod/>
<ContMod/>
<ContMod/>
<p style="width: 300px;
          background: aquamarine">
    &emsp;Even though we have called the
    same component many times, the
    <i>'JS'</i> part that we defined with the
    <b>context="module"</b>
    only works once. In this way,
    I was able to change the variables
    in it with a single component. <br><br>
    &emsp;If we want to share values to different
    components we can use <i>stores</i> for that
    (as it is said in the documentation.)
</p>


