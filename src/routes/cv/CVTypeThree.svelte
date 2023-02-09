<script lang="ts">
  import type { CVTypeThree } from '$lib/types';

  export let type: 'Publications';
  export let items: CVTypeThree[] = [];
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
        <div class="font-extralight">
          {item.description}
        </div>
      </div>
    {/each}
  </div>
</div>
