<script context="module">
    /*Runs once when the module first evaluates,
    rather than for each component instance. */
    let totalCount = 0
    export function tot() {
        return totalCount;
    }
</script>


<script>
    let counter = 0;
    function addOne() {
        counter++;
        totalCount++;
        console.log(totalCount);
    }
</script>

<button on:click={addOne}>Add One to --> ({counter})</button>
<br>

