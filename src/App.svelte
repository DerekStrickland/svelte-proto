<script>
  import Jobs from "./Jobs.svelte";
  import Supplies from "./Supplies.svelte";
  import SupplyChain from "./SupplyChain.svelte";
  import Food from "./Food.svelte";

  export let selectedTab = "Jobs";

  function changeTab(tab) {
    console.log(tab);
    selectedTab = tab;
  }
</script>

<style>
  ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    overflow: hidden;
    background-color: #333333;
    width: 100%;
  }

  li {
    float: left;
    color: white;
    width: 25%;
    text-align: center;
    padding-top: 20px;
    padding-bottom: 20px;
    cursor: "pointer";
  }
</style>

<main>
  <div>
    <ul>
      <li on:click|preventDefault={() => changeTab('Jobs')}>Jobs</li>
      <li on:click|preventDefault={() => changeTab('Supplies')}>Supplies</li>
      <li on:click|preventDefault={() => changeTab('SupplyChain')}>
        Supply Chain
      </li>
      <li on:click|preventDefault={() => changeTab('Food')}>Food</li>
    </ul>
  </div>
  {#if selectedTab === 'Jobs'}
    <Jobs />
  {:else if selectedTab === 'Supplies'}
    <Supplies />
  {:else if selectedTab === 'SupplyChain'}
    <SupplyChain />
  {:else}
    <Food />
  {/if}
</main>
