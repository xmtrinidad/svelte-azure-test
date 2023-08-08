<script lang="ts">
  let yearly = false;

  function onYearlyToggle() {
    yearly = !yearly;
  }
</script>

<div class="monthly-yearly-toggle">
  <button on:click={onYearlyToggle}>
    <span class="text">Monthly</span>
    <div class="switch">
      <div class:yearly class="toggle"></div>
    </div>
    <span class="text">Yearly</span>
  </button>
</div>


<style>
  .monthly-yearly-toggle {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 24px;
    background-color: #f8f9fe;
    padding: 16px;
    border-radius: 4px;
  }

  button {
    margin: 0;
    background-color: transparent;
    border: none;
    color: #808089;
    font-weight: bold;
    cursor: pointer;
    display: flex;
    align-items: center;
    gap: 24px;
    padding: 0 8px;
  }

  .switch {
    display: flex;
    align-items: center;
    background-color: #03295a;
    width: 44px;
    padding: 4px 6px;
    border-radius: 12px;
  }

  .toggle {
    width: 12px;
    height: 12px;
    background-color: #fff;
    border-radius: 100%;
    position: relative;
    left: 0px;
    transition: left 0.2s ease-in-out;
  }

  .toggle.yearly {
    left: 20px;
  }
</style>