<script>
  import { LANGUAGES } from '$lib/data/languages';
</script>

<div class="pb-4">
  <div class="grid lg:grid-cols-12 lg:gap-x-8">
    <div class="col-span-4 text-right" />
    <div class="col-span-8">
      <div class="mb-4 inline-block border border-white px-2 pb-1 text-lg sm:text-xl">
        Languages
      </div>
    </div>
  </div>

  <div class="grid lg:grid-cols-12 lg:gap-x-8">
    <div class="col-span-4 text-right" />
    <div class="col-span-8">
      <div class="grid grid-cols-2 md:w-2/3">
        {#each LANGUAGES as item}
          <div>
            {item.language}:
            <span class="font-extralight">{item.proficiency}</span>
          </div>
        {/each}
      </div>
    </div>
  </div>
</div>
