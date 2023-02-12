<script lang="ts">
  import type { CVTypeOne } from '$lib/types';

  export let type: 'Awards' | 'Education' | 'Teaching' | 'Residencies';
  export let items: CVTypeOne[] = [];
</script>

<div class="pb-4">
  <div class="grid lg:grid-cols-12 lg:gap-x-8">
    <div class="col-span-4 text-right" />
    <div class="col-span-8">
      <div class="mb-4 inline-block border border-white px-2 pb-1 text-lg sm:text-xl">{type}</div>
    </div>
  </div>

  <!-- Template for Desktop devices -->
  <div class="hidden lg:block">
    {#each items as item}
      <div class="mb-4">
        <div class="grid grid-flow-col grid-cols-12 gap-x-8">
          <div class="col-span-4 text-right">
            <div class="text-xl font-light">{item.location}</div>
          </div>
          <div class="col-span-8">
            <div class="text-xl">{item.title}</div>
          </div>
        </div>
        <div class="mb-2 grid grid-cols-12 gap-x-8">
          <div class="col-span-4 text-right">
            <div class="text-lg font-extralight">{item.date}</div>
          </div>
          <div class="col-span-8">
            <div class="text-lg font-extralight">{item.subtitle}</div>
          </div>
        </div>
        <div class="grid grid-cols-12 gap-x-8">
          <div class="col-span-4 text-right" />
          <div class="col-span-8">
            <div class="font-extralight">
              {item.description}
            </div>
          </div>
        </div>
      </div>
    {/each}
  </div>

  <!-- Template for Mobile devices -->
  <div class="lg:hidden">
    {#each items as item}
      <div class="mb-4">
        <div class="flex justify-between">
          <div class="text-lg">{item.title}</div>
          <div class="text-right text-lg font-light">{item.location}</div>
        </div>
        <div class="mb-2 flex justify-between">
          <div class="font-extralight">{item.subtitle}</div>
          <div class="text-right font-extralight">{item.date}</div>
        </div>
        <div class="text-sm font-extralight">
          {item.description}
        </div>
      </div>
    {/each}
  </div>
</div>
