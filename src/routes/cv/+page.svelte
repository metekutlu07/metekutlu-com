<script lang="ts">
  import { RESIDENCIES } from '$lib/data/residencies';
  import { CONFERENCES } from '$lib/data/conferences';
  import { EDUCATIONS } from '$lib/data/educations';
  import { PUBLICATIONS } from '$lib/data/publications';
  import GoHome from './GoHome.svelte';
  import CvTypeOne from './CVTypeOne.svelte';
  import CvTypeTwo from './CVTypeTwo.svelte';
  import CvTypeThree from './CVTypeThree.svelte';
  import LanguagesSection from './LanguagesSection.svelte';
</script>

<GoHome />
<div class="px-4 pt-12 pb-4 md:px-6 md:pb-6 lg:mx-auto lg:max-w-5xl">
  <CvTypeOne type="Residencies" items={RESIDENCIES} />
  <CvTypeTwo type="Conferences" items={CONFERENCES} />
  <CvTypeOne type="Education" items={EDUCATIONS} />
  <CvTypeThree type="Publications" items={PUBLICATIONS} />
  <LanguagesSection />
</div>
