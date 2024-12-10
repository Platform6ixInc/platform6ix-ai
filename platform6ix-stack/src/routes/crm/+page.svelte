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

<div class="mx-auto flex w-full flex-col gap-4 md:max-w-[58rem]">
    <h2 class="font-heading text-3xl leading-[1.1] sm:text-3xl md:text-6xl">
      Offside CRM
    </h2>

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
        </div>
    </section>
</div>