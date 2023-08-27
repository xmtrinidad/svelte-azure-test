<script>
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

</script>


<FormShell step={activeForm.step}>
  <svelte:component this={activeForm.component}  />
  <!-- <PersonalInfo /> -->
  <!-- <SelectPlan /> -->
</FormShell>