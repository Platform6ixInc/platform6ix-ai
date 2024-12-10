<script lang="ts">
	import { Button } from "$components/ui/button";
	import Subhero from "../Subhero.svelte";
	import UserAuthForm from "../UserAuthForm.svelte";
	import { invalidate } from '$app/navigation'
	import { onMount } from 'svelte'

	export let data

	let { supabase, session } = data
	$:  ({ supabase, session } = data)

	onMount(() => {
		const { data } = supabase.auth.onAuthStateChange((event, _session) => {
			if (_session?.expires_at !== session?.expires_at) {
				invalidate('supabase:auth')
			}
		})

		return () => data.subscription.unsubscribe()
	})
</script>
<section class="space-y-6 pb-8 pt-6 md:pb-12 md:pt-10 lg:py-32">
	<div class="container flex max-w-[64rem] flex-col items-center gap-4 text-center">
		{#if data.session}

		<ul class="mx-2 py-2 text-sm text-gray-700 dark:text-gray-200" aria-labelledby="dropdownHoverProfileButton">
		<li>
		<form action="/logout" method="POST">
			<button type="submit" class="btn btn-primary">Logout</button>
		</form>
		</li>
		</ul>
		{:else}


		<a
		href="/register"
		class="mx-2 text-sm font-medium text-muted-foreground transition-colors hover:text-primary"
		>
			Register
		</a>
		<a
		href="/login"
		class="mx-2 text-sm font-medium text-muted-foreground transition-colors hover:text-primary"
		>
			Login
		</a>
		{/if}
	  <a
		href="https://discord.gg/tGesbuF2Ch"
		class="rounded-2xl bg-muted px-4 py-1.5 text-sm font-medium"
		target="_blank"
	  >
		Join us on discord
	  </a>
	  <h1 class="font-heading text-3xl sm:text-5xl md:text-6xl lg:text-7xl">
		OffsideAI GenML - The GenAI Platform for Enterprise Data Engineering and ML-Ops
	  </h1>
	  <p class="max-w-[42rem] leading-normal text-muted-foreground sm:text-xl sm:leading-8">
		AI Alignment Research,Model Training Pipelines,  ML Ops Deployments, AI Application Development
	  </p>
	  <div class="space-x-4">
		<a href="https://github.com/offsideAI/ModelHub" class="lg">
		  Get Started
		</a>
		<a
		  href="https://github.com/offsideAI/ModelHub"
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
		OffsideAI develops AI applications for enterprise use-cases
	  </h2>
	  <p class="max-w-[85%] leading-normal text-muted-foreground sm:text-lg sm:leading-7">
		OffsideAI is open source <br />{" "}
		The code is available on{" "}
		<a
		  href="#"
		  target="_blank"
		  rel="noreferrer"
		  class="underline underline-offset-4"
		>
		  GitHub
		</a>
		.{" "}
	  </p>
		<a
		  href="#"
		  target="_blank"
		  rel="noreferrer"
		  class="flex"
		>
		  <div class="flex h-10 w-10 items-center justify-center space-x-2 rounded-md border border-muted bg-muted">
			<svg
			  xmlns="http://www.w3.org/2000/svg"
			  fill="currentColor"
			  viewBox="0 0 24 24"
			  class="h-5 w-5 text-foreground"
			>
			  <path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"></path>
			</svg>
		  </div>
		  <div class="flex items-center">
			<div class="h-4 w-4 border-y-8 border-l-0 border-r-8 border-solid border-muted border-y-transparent"></div>
			<div class="flex h-10 items-center rounded-md border border-muted bg-muted px-4 font-medium">
			  21 stars on GitHub
			</div>
		  </div>
		</a>
	</div>
  </section>
