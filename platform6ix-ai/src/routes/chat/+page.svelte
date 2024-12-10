<script lang="ts">
    import type { PageData } from './$types';
	import { Input } from "$components/ui/input";
    import Subhero from "../Subhero.svelte";
    import { useChat } from 'ai/svelte';

    const { messages, handleSubmit, input } = useChat({
        api: "/chat",

    });

</script>


<section class="space-y-6 pb-4 pt-3 md:pb-12 md:pt-5 lg:py-8">
	<div class="container flex max-w-[64rem] flex-col items-center gap-4 text-center">
	  <a
		href=""
		class="rounded-2xl bg-muted px-4 py-1.5 text-lg font-medium"
		target="_blank"
	  >
		Welcome to Platform6ix Assistant 
	  </a>



    <form on:submit={handleSubmit}>
        <Input bind:value={$input}  placeholder="Chat with Platform6ix..."
		class="h-9 md:w-[100px] lg:w-[300px]"/>
        <br/>
        <button 
        type="submit"
        class="rounded-2xl bg-muted px-4 py-1.5 text-lg font-medium"
        >Let's Chat</button>
    </form> 

        <ul>
            {#each $messages as message}
                <code>{message.role} says ... {message.content}</code><br/>
            {/each}
        </ul>
	</div>
  </section>
