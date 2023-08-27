<script>
    import FormHeader from "./FormHeader.svelte";

</script>

<div class="personal-info">
  <FormHeader header="Personal Info" text="Please provide your name, email address, and phone number"></FormHeader>
  <form action="">
    <div class="input-container">
      <label for="name">Name</label>
      <input name="name" type="text" id="name" placeholder="Enter your name" />
    </div>
    <div class="input-container">
      <label for="email">Email Address</label>
      <input name="email" type="text" id="email" placeholder="Enter your email" />
    </div>
    <div class="input-container">
      <label for="phone">Phone Number</label>
      <input name="phone" type="text" id="phone" placeholder="Enter your phone number" />
    </div>
  </form>
</div>


<style>
  form {
    margin: 24px 0;
    display: flex;
    flex-direction: column;
    gap: 16px;
  }

  .input-container {
    display: flex;
    flex-direction: column;
    gap: 4px;
    font-weight: 600;
  }

  label {
    font-size: 0.875rem;
    color: #465172;
  }

  input {
    padding: 12px 16px;
    border: 1px solid #465172;
    border-radius: 4px;
    font-size: 1rem;
    color: #465172;
    background-color: #fff;
  }
</style>