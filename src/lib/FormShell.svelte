<script>
    import MultistepProgress from "./MultistepProgress.svelte";


</script>

<div class="form-shell">
  <MultistepProgress />
  <div class="active-form">
    <slot></slot>
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

  .active-form {
    margin: 24px auto;
    min-width: 500px;
  }
</style>