<script>
    let inputvalue;
    const searchFn = () => {
        console.log("searching:", inputvalue);
    };
    const handleKeyDownFn = (e) => {
        e.key === "Enter" ? console.log("searching:", inputvalue) : null;
    };
    const closeDialogFn = (e) => {
        const dialog = document.querySelector("#searchDialog");
        e.target === dialog ? dialog.close() : null;
    };
</script>

<dialog id="searchDialog" on:keydown={handleKeyDownFn} on:click={closeDialogFn}>
    <div>
        <input type="text" placeholder="Spirited Away" bind:value={inputvalue} />
        <button on:click={searchFn}>Search</button>
    </div>
</dialog>