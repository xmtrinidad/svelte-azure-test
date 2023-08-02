<script>
  import FormHeader from "./FormHeader.svelte";

  const plans = [
    {
      name: "Arcade",
      price: "$9/mo",
      icon: "arcade",
    },
    {
      name: "Pro",
      price: "$19/mo",
      icon: "pro",
    },
    {
      name: "Business",
      price: "$49/mo",
      icon: "business",
    },
  ];
</script>

<div class="personal-info">
  <FormHeader header="Select your plan" text="You have the option of monthly or yearly billing"></FormHeader>
  <form action="">
    {#each plans as plan}
      <button class="price-container">
        <div class="icon">{plan.icon}</div>
        <div class="price-name-container">
          <span class="price-name">{plan.name}</span>
          <span class="price">{plan.price}</span>
        </div>
      </button>
    {/each}
  </form>
</div>


<style>

form {
  margin: 24px 0;
  display: flex;
  gap: 16px;
}

.price-container {
  border: none;
  background-color: #f8f9fe;
  border: 1px solid #5a529e;
  width: 132px;
  height: 140px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 12px;
  border-radius: 8px;
  cursor: pointer;
  text-align: left;
}

.price-name-container {
  display: flex;
  flex-direction: column;
  gap: 4px;
}

.price-name {
  font-weight: bold;
}

.price {
  color: #81808c;
}



</style>