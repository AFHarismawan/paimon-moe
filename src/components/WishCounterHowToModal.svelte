<script>
  import { mdiPencil, mdiStar } from '@mdi/js';
  import Icon from './Icon.svelte';
  import Checkbox from '../components/Checkbox.svelte';

  export let setManualInput;
  export let settings;

  let enableManual = settings.manualInput;

  function toggleManual() {
    setManualInput(enableManual);
  }

  $: enableManual, toggleManual();
</script>

<div>
  <h1 class="font-display text-white text-xl mb-4">Wish Counter Help & Settings</h1>
  <div class="text-white p-2 bg-background rounded-xl">
    <div class="py-2 pl-4">
      <Checkbox disabled={false} bind:checked={enableManual}
        ><span class="select-none cursor-pointer">Enable Manual Input</span></Checkbox
      >
    </div>
    <p class="text-red-300">
      Using the Auto Import and manual input together is not recommended, still need some testing!
    </p>
    <p>Consider using the Auto Import first, access it on button beside the button you click to open this How To</p>
  </div>
  <h1 class="font-display text-white text-xl mt-6 mb-4">How to use manual input</h1>
  <div class="text-white p-2 bg-background rounded-xl mt-4">
    <p class="mb-2">After you do 1 pull Wish:</p>
    <p class="mb-2">
      Press
      <b class="rounded-lg px-2 py-1 border-white border inline-flex items-center">+1</b>
      when you get
      <span class="inline-flex items-center"
        >3
        <Icon path={mdiStar} size={0.7} /></span
      >
    </p>
    <p class="mb-2">
      Press
      <b class="rounded-lg px-2 py-1 border-white border inline-flex items-center"
        >Get 4
        <Icon path={mdiStar} size={0.7} /></b
      >
      when you get
      <span class="inline-flex items-center"
        >4
        <Icon path={mdiStar} size={0.7} /></span
      >
    </p>
    <p class="mb-2">
      Press
      <b class="rounded-lg px-2 py-1 border-white border inline-flex items-center"
        >Get 5
        <Icon path={mdiStar} size={0.7} /></b
      >
      when you get
      <span class="inline-flex items-center"
        >5
        <Icon path={mdiStar} size={0.7} /></span
      >
    </p>
    <p class="text-gray-400">
      It will automatically add the lifetime pulls,
      <span class="inline-flex items-center"
        >5
        <Icon path={mdiStar} size={0.7} /></span
      >
      and
      <span class="inline-flex items-center"
        >4
        <Icon path={mdiStar} size={0.7} /></span
      >
      pity
    </p>
    <p class="text-gray-400">
      When the
      <span class="inline-flex items-center"
        >4
        <Icon path={mdiStar} size={0.7} /></span
      >
      pity reach 10, it will automatically reset to 0
    </p>
    <p class="text-gray-400">
      When the
      <span class="inline-flex items-center"
        >5
        <Icon path={mdiStar} size={0.7} /></span
      >
      pity reach 90, it will automatically reset to 0
    </p>
  </div>
  <div class="text-white p-2 bg-background rounded-xl mt-4">
    For when you do 10 pulls Wish, press the
    <b class="rounded-lg px-2 py-1 border-white border inline-flex items-center">+10</b>
    button,
    <span class="text-gray-400"
      >but the pity counter won't be accurate, because there is no way to tell when the drop occur (maybe you got it on
      the 1st or even the 10th). To make the counter still accurate, you need to check it on the history table and add
      it 1 by 1 like you do 1 pull Wish.</span
    >
  </div>
  <div class="text-white p-2 bg-background rounded-xl mt-4">
    You can also press
    <b class="rounded-lg px-2 py-1 border-white border inline-flex items-center"><Icon path={mdiPencil} size={0.7} /></b
    >
    button to edit the values manually!
  </div>
  <div class="text-white p-2 bg-background rounded-xl mt-4">
    Press the arrow on the bottom to see your pulls detail. A popup will show when you get <span
      class="inline-flex items-center"
      >5
      <Icon path={mdiStar} size={0.7} /></span
    >
    or
    <span class="inline-flex items-center"
      >4
      <Icon path={mdiStar} size={0.7} /></span
    >. Or you can add or edit the table manually.
  </div>
</div>
