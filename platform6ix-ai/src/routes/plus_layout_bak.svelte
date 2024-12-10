<script lang="ts">
	import '../app.postcss';
	import { Avatar, AvatarFallback, AvatarImage } from "$components/ui/avatar";
	import MainNav from './MainNav.svelte';
	import Search from "./Search.svelte";
	import Footer from './Footer.svelte';
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

<div class="flex flex-col">
	<header class="container z-40 bg-background">
	  <div class="flex h-20 items-center justify-between py-6">
		<a href="/">
		<img src="/favicon.png" alt="Platform6ix" class="mx-4 px-1 h-8 w-8 md:h-10 md:w-10" />
		</a>
		<a
		href="/"
		class="mx-2 text-sm font-medium text-muted-foreground transition-colors hover:text-primary"
		>
		Home
		</a>

		<a
		href="/chat"
		class="mx-2 text-sm font-medium text-muted-foreground transition-colors hover:text-primary"
		>
		Chat
		</a>

		<!-- <MainNav class="mx-6" /> -->
		<div class="ml-auto flex items-center space-x-4">
			<div class="hidden md:flex space-x-2">
			<Search />
			<!-- TODO-FIXME-CLEANUP <Avatar class="h-8 w-8">
				<AvatarImage src="/avatars/01.png" alt="@shadcn" />
				<AvatarFallback>SC</AvatarFallback>
			</Avatar>
			-->
			</div>

		</div>
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
	  </div>
	</header>
	<div class="flex-1 space-y-4 p-8 pt-6">
		<div class="flex flex-col md:flex-row items-center justify-center">
		</div>
		<slot />	
	</div>
	<!-- SiteFooter -->
	<Footer/>
</div>
