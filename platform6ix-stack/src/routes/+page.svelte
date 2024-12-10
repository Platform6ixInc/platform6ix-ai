<script lang="ts">
	import { Button } from "$components/ui/button";
	import Subhero from "./Subhero.svelte";
	import UserAuthForm from "./UserAuthForm.svelte";
</script>
<section class="space-y-6 pb-8 pt-6 md:pb-6 md:pt-5 lg:py-4">
	<div class="container flex max-w-[64rem] flex-col items-center gap-4 text-center">
	  <img src="logo.svg" alt="Platform6ix" class="w-24 h-24 sm:w-32 sm:h-32 md:w-40 md:h-40 lg:w-48 lg:h-48" />
	  <a
		href="https://apps.apple.com/us/app/platform6ix/id1631784184"
		class="rounded-2xl bg-muted px-4 py-1.5 text-sm font-medium"
		target="_blank"
	  >
		Platform6ix on App Store
	  </a>
	  <h1 class="font-heading text-3xl sm:text-5xl md:text-6xl lg:text-7xl">
		Platform6ix | The Agentic AI SaaS Platform
	  </h1>
	  <p class="max-w-[42rem] leading-normal text-muted-foreground sm:text-xl sm:leading-8">
		AI Concierge Apps, AI Assistants, Model Training,  Vector DB,  ML Ops,  Pipeline Deployments, Spatial Computing
	  </p>
	  <div class="space-x-4">
		<a href="https://github.com/platform6ix/ModelHub" class="lg">
		  Get Started
		</a>
		<a
		  href="https://github.com/platform6ix/ModelHub"
		  target="_blank"
		  rel="noreferrer"
		  class="lg"
		>
		  Model Hub
		</a>
	  </div>
	</div>
  </section>
  <Subhero />
  <section id="open-source" class="container py-8 md:py-12 lg:py-24">
	<div class="mx-auto flex max-w-[58rem] flex-col items-center justify-center gap-4 text-center">
	  <h2 class="font-heading text-3xl leading-[1.1] sm:text-3xl md:text-6xl">
		Proudly Open Source
	  </h2>
	  <p class="max-w-[85%] leading-normal text-muted-foreground sm:text-lg sm:leading-7">
		Platform6ix is open source <br />{" "}
		The code is available on{" "}
		<a
		  href="https://github.com/platform6ix"
		  target="_blank"
		  rel="noreferrer"
		  class="underline underline-offset-4"
		>
		  GitHub
		</a>
		.{" "}
	  </p>
		<a
		  href="https://www.producthunt.com/products/platform6ix"
		  target="_blank"
		  rel="noreferrer"
		  class="flex"
		>
		  <div class="flex h-10 w-10 items-center justify-center space-x-2 rounded-md border border-muted bg-muted">
			<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="#ffffff" stroke-width="0.75" stroke-linecap="round" stroke-linejoin="round" class="h-12 w-12 lucide lucide-package">
				<path d="M16.5 9.4 7.55 4.24"/><path d="M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"/><polyline points="3.29 7 12 12 20.71 7"/><line x1="12" x2="12" y1="22" y2="12"/>
			</svg>
		  </div>
		  <div class="flex items-center">
			<div class="h-4 w-4 border-y-8 border-l-0 border-r-8 border-solid border-muted border-y-transparent"></div>
			<div class="flex h-10 items-center rounded-md border border-muted bg-muted px-4 font-medium">
			  Featured on ProductHunt
			</div>
		  </div>
		</a>
	</div>
  </section>
