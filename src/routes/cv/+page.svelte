<script lang="ts">
  import { INTERNSHIPS } from '$lib/data/internships';
  import { AWARDS } from '$lib/data/awards';
  import { TEACHING } from '$lib/data/teaching';
  import { RESIDENCIES } from '$lib/data/residencies';
  import { CONFERENCES } from '$lib/data/conferences';
  import { EDUCATIONS } from '$lib/data/educations';
  import { PUBLICATIONS } from '$lib/data/publications';
  import GoHome from './GoHome.svelte';
  import CvTypeOne from './CVTypeOne.svelte';
  import CvTypeTwo from './CVTypeTwo.svelte';
  import CvTypeThree from './CVTypeThree.svelte';
  import LanguagesSection from './LanguagesSection.svelte';
  import DownloadSection from './DownloadSection.svelte';
</script>

<GoHome />
<div class="mx-auto max-w-5xl px-4 pt-12 pb-4 md:px-6 md:pb-6">
  <CvTypeOne type="Residencies" items={RESIDENCIES} />
  <CvTypeOne type="Awards" items={AWARDS} />
  <CvTypeOne type="Teaching" items={TEACHING} />
  <CvTypeTwo type="Conferences" items={CONFERENCES} />
  <CvTypeThree type="Publications" items={PUBLICATIONS} />
  <CvTypeOne type="Education" items={EDUCATIONS} />
  <CvTypeTwo type="Internships" items={INTERNSHIPS} />

  <LanguagesSection />
  <DownloadSection />
</div>
