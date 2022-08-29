<script>
    // Any data from our storage
    import {storeData} from "./store";

    // See data types
    console.log(storeData) //typeOf: object

    // Prefix stores with " $ " sign.
    console.log($storeData) //typeOf: string

    // Updating storeData with Input value "bind:value={}"
    function updateData() {
        storeData.update(value => value = $storeData)
        console.log('updated data: ',$storeData)
    }

    // Set data to a 'default'
    function setData() {
        storeData.set('default');
        console.log('set data: ', $storeData)
    }
</script>

<!--
Bound with Input.
Changes are rendering on the screen Immediately
-->
<h1>{$storeData}</h1>

<article>
<input type="text" bind:value={$storeData}><br>
<button on:click={setData}>Set Data</button>
<button on:click={updateData}>Update Data</button>
</article>
<hr>
