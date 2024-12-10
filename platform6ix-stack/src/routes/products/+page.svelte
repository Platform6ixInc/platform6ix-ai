<script lang="ts">
    import OffsideAiCrm from '../Platform6ixCrm.svelte';
	import OffsideAiVision from '../Platform6ixVision.svelte';
import type { PageData } from './$types';
    
    export let data: PageData;
</script>


<section class="container flex flex-col  gap-6 py-8 md:max-w-[64rem] md:py-12 lg:py-24">
   <OffsideAiCrm />
   <OffsideAiVision /> 
    <div class="mx-auto flex w-full max-w-[58rem] flex-col gap-4">
      <p class="max-w-[85%] leading-normal text-muted-foreground sm:leading-7">
        <strong>Platform6ix is the generative AI platform for enterprise.{" "}</strong>
      </p>
    </div>
  </section>