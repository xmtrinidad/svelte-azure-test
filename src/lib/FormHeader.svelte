<script>
  export let header = '';
  export let text = '';
</script>

<div class="form-header">
  <h1>{header}</h1>
  <p>{text}</p>
</div>

<style>
  h1 {
    font-size: 2.25rem;
    color: #052757;
    margin: 0;
  }

  p {
    color: #b1b2b6;
  }
</style>