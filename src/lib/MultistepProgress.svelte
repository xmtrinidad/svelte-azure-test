<script>
  const steps = [
    { num: 1, label: "STEP 1", title: "YOUR INFO", active: true },
    { num: 2, label: "STEP 2", title: "SELECT PLAN", active: false },
    { num: 3, label: "STEP 3", title: "ADD-ONS", active: false },
    { num: 4, label: "STEP 4", title: "SUMMARY", active: false }
  ];
</script>

<div class="multistep-progress">
  <svg xmlns="http://www.w3.org/2000/svg" width="274" height="568" fill="none" viewBox="0 0 274 568"><rect width="274" height="568" fill="#483EFF" rx="10"/><mask id="a" width="274" height="568" x="0" y="0" maskUnits="userSpaceOnUse" style="mask-type:alpha"><rect width="274" height="568" fill="#fff" rx="10"/></mask><g mask="url(#a)"><path fill="#6259FF" fill-rule="evenodd" d="M-34.692 543.101C3.247 632.538 168.767 685.017 211.96 612.52c43.194-72.497-66.099-85.653-104.735-160.569-38.635-74.916-68.657-121.674-124.482-104.607-55.824 17.068-55.375 106.32-17.436 195.757Z" clip-rule="evenodd"/><path fill="#F9818E" fill-rule="evenodd" d="M233.095 601.153c60.679-28.278 92.839-143.526 41.875-171.528-50.965-28.003-57.397 47.579-108.059 75.987-50.662 28.408-82.14 50.207-69.044 88.241 13.096 38.034 74.549 35.578 135.228 7.3Z" clip-rule="evenodd"/><path stroke="#fff" stroke-linecap="round" stroke-linejoin="bevel" stroke-width="5" d="m165.305 469.097 10.607-10.806M209.461 474.581l-12.506-10.503M187.56 488.991l-6.908 14.798"/><path fill="#FFAF7E" d="M.305 546.891c37.003 0 67-29.997 67-67s-29.997-67-67-67-67 29.997-67 67 29.997 67 67 67Z"/></g></svg>
  <div class="steps">
    {#each steps as step}
      <button class="step">
        <span class="step-number {step.active ? 'active' : ''}">{step.num}</span>
        <div class="step-label-container">
          <span class="step-label">{step.label}</span>
          <span class="step-title">{step.title}</span>
        </div>
      </button>
    {/each}
  </div>
</div>

<style>
  .multistep-progress {
    position: relative;
  }
  .steps {
    display: flex;
    flex-direction: column;
    gap: 20px;
    position: absolute;
    top: 0;
    width: 100%;
    padding: 24px;
  }

  .steps button {
    background-color: transparent;
    border: none;
    display: flex;
    align-items: center;
    gap: 16px;
    cursor: pointer;
  }

  .step-number {
    width: 36px;
    height: 36px;
    border-radius: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: transparent;
    color: #fff;
    border: 1px solid #fff;
  }

  .step-number.active {
    background-color: #c0e3ff;
    color: #000;
  }

  .step-label-container {
    display: flex;
    flex-direction: column;
    gap: 4px;
    text-align: left;;
  }

  .step-label {
    color: #8c88ff;
  }

  .step-title {
    font-weight: bold;
    color: #fff;
  }
</style>