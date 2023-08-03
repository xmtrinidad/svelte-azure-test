<script>
  import FormHeader from "./FormHeader.svelte";
  import ArcadeIcon from "./icons/ArcadeIcon.svelte";
    import BusinessIcon from "./icons/BusinessIcon.svelte";
    import ShieldIcon from "./icons/ShieldIcon.svelte";

  let plans = [
    {
      name: "Arcade",
      price: "$9/mo",
      icon: ArcadeIcon,
      active: true
    },
    {
      name: "Pro",
      price: "$19/mo",
      icon: ShieldIcon,
      active: false
    },
    {
      name: "Business",
      price: "$49/mo",
      icon: BusinessIcon,
      active: false
    },
  ];

  function onPlanClick(plan) {
    plans.forEach(p => p.active = false);
    plan.active = true;

    plans = plans;
  }
</script>

<div class="personal-info">
  <FormHeader header="Select your plan" text="You have the option of monthly or yearly billing"></FormHeader>
  <form action="">
    {#each plans as plan}
      <button on:click={() => onPlanClick(plan)} class="price-container {plan.active ? 'active' : ''}">
        <div class="icon-container">
          <svelte:component this={plan.icon} />
        </div>
        <div class="price-name-container">
          <span class="price-name">{plan.name}</span>
          <span class="price">{plan.price}</span>
        </div>
      </button>
    {/each}
  </form>
</div>


<style>

.personal-info :global(svg) {
  fill: #fff;
}

form {
  margin: 24px 0;
  display: flex;
  gap: 16px;
}

.price-container {
  border: none;
  background-color: #fff;
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

.price-container.active {
  background-color: #f8f9fe;
}

.icon-container {
  width: 36px;
  height: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 100%;
}

.price-container:first-child .icon-container {
  background-color: #ffab7c;
}

.price-container:nth-child(2) .icon-container {
  background-color: #ff7b89;
}

.price-container:last-child .icon-container {
  background-color: #4341ff;
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