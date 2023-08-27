<script>
    import MultistepProgress from "./MultistepProgress.svelte";
    export let step = 1;
</script>

<div class="form-shell">
  <MultistepProgress />
  <div class="form-container">
    <div class="active-form">
      <slot></slot>
    </div>
    <div class="next-form-buttons">
      {#if step === 1 || step === 4}
        <div></div>
      {:else}
        <button class="go-back-button">Go Back</button>
      {/if}
      <button class="next-button">Next Step</button>
    </div>
  </div>
</div>

<style>
  .form-shell {
    padding: 16px;
    box-shadow: 0 3px 6px rgba(0,0,0,0.16), 0 3px 6px rgba(0,0,0,0.23);
    height: 600px;
    display: flex;
    background-color: #fff;
  }

  .form-container {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    max-width: 540px;
    margin: 0 auto;
  }

  .next-form-buttons {
    display: flex;
    justify-content: space-between;
    margin-top: 60px;
  }

  .next-form-buttons button {
    border: none;
    padding: 12px 24px;
    border-radius: 4px;
    cursor: pointer;
  }

  .next-form-buttons .go-back-button {
    background-color: transparent;
    color: #01295a;
    font-weight: 600;
  }

  .next-form-buttons .next-button {
    background-color: #01295a;
    color: #fff;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.25);
  }
</style>