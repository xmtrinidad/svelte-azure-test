<script lang="ts">
  import FormShell from "$lib/FormShell.svelte";
  import PersonalInfo from "$lib/PersonalInfo.svelte";
  import SelectPlan from "$lib/SelectPlan.svelte";

  const forms = [
    {
      step: 1,
      component: PersonalInfo
    },
    {
      step: 2,
      component: SelectPlan
    }
  ];

  let activeForm = forms[0];
  

  function onFormAction(e: Event) {
    const target = e.target as HTMLButtonElement;

    if (target.id === "next-button") {
      activeForm = forms[1];
    } else if (target.id === "prev-button") {
      // activeForm = forms[activeForm.step - 2];
    }
  }
</script>


<FormShell step={activeForm.step} on:click={onFormAction}>
  <svelte:component this={activeForm.component}  />
  <!-- <PersonalInfo /> -->
  <!-- <SelectPlan /> -->
</FormShell>