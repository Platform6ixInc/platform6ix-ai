<script lang="ts">
	import type { PageData } from "./$types";
  import { Button } from "$components/ui/button";
	import UserAuthForm from "../UserAuthForm.svelte";

  export let data: PageData
</script>


            {#if data.session}
              <p>Welcome, {data.session.user.email}</p>
              <ul class="mx-2 py-2 text-sm text-gray-700 dark:text-gray-200" aria-labelledby="dropdownHoverProfileButton">
                <li>
                <form action="/logout" method="POST">
                  <button type="submit" class="btn btn-primary">Logout</button>
                </form>
                </li>
              </ul>
            {:else}
            <div class="container relative hidden h-[800px] flex-col items-center justify-center md:grid lg:max-w-none lg:grid-cols-2 lg:px-0">
              <Button
              href="/login"
              variant="ghost"
              class="absolute right-4 top-4 md:right-8 md:top-8"
            >
              Go to Login
            </Button>
            <div
              class="relative hidden h-full flex-col bg-muted p-10 text-white dark:border-r lg:flex"
            >
              <div
                class="absolute inset-0 bg-cover"
                style="
                  background-image:
                    url(bluesky_bg.jpg);"
              />
              <div class="relative z-20 flex items-center text-lg font-medium">
                OffsideAI 
              </div>
              <div class="relative z-20 mt-auto">
                <blockquote class="space-y-2">
                  <p class="text-lg">
                    &ldquo;Cogito Ergo Sum&rdquo;
                  </p>
                  <footer class="text-sm">René Descartes</footer>
                </blockquote>
              </div>
            </div>
            <div class="lg:p-8">
              <div
                class="mx-auto flex w-full flex-col justify-center space-y-6 sm:w-[350px]"
              >
                <div class="flex flex-col space-y-2 text-center">
                  <h1 class="text-2xl font-semibold tracking-tight">
                    Create an account
                  </h1>
                  <p class="text-sm text-muted-foreground">
                    Enter your email below to create your account
                  </p>
                </div>
                
                <form class="space-y-6" action="?/register" method="POST">
                  <div>
                    <label for="email" class="block text-sm font-medium leading-6 text-white">Email address</label>
                    <div class="mt-2">
                      <input id="email" name="email" type="email" autocomplete="email" required class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-stone-500 sm:text-sm sm:leading-6">
                    </div>
                  </div>
            
                  <div>
                    <div class="flex items-center justify-between">
                      <label for="password" class="block text-sm font-medium leading-6 text-white">Password</label>
                      <div class="text-sm">
                        <a href="/forgotpassword" class="font-semibold text-slate-400 hover:text-stone-300">Forgot password?</a>
                      </div>
                    </div>
                    <div class="mt-2">
                      <input id="password" name="password" type="password" autocomplete="current-password" required class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-stone-500 sm:text-sm sm:leading-6">
                    </div>
                  </div>
            
                  <div>
                    <button type="submit" class="flex w-full justify-center rounded-md bg-slate-500 px-3 py-1.5 text-sm font-semibold leading-6 text-white shadow-sm hover:bg-stone-400 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-stone-500">Sign Up</button>
                  </div>
                </form>

                <p class="px-8 text-center text-sm text-muted-foreground">
                  By clicking continue, you agree to our{" "}
                  <a
                    href="/terms"
                    class="underline underline-offset-4 hover:text-primary"
                  >
                    Terms of Service
                  </a>{" "}
                  and{" "}
                  <a
                    href="/privacy"
                    class="underline underline-offset-4 hover:text-primary"
                  >
                    Privacy Policy
                  </a>
                  .
                </p>
              </div>
            </div> 

            </div>
            <!-- START OF EXISTING REGISTER  
            <div class="mt-10 sm:mx-auto sm:w-full sm:max-w-sm">
              <form class="space-y-6" action="?/register" method="POST">
                <div>
                  <label for="email" class="block text-sm font-medium leading-6 text-white">Email address</label>
                  <div class="mt-2">
                    <input id="email" name="email" type="email" autocomplete="email" required class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-stone-500 sm:text-sm sm:leading-6">
                  </div>
                </div>
          
                <div>
                  <div class="flex items-center justify-between">
                    <label for="password" class="block text-sm font-medium leading-6 text-white">Password</label>
                    <div class="text-sm">
                      <a href="/forgotpassword" class="font-semibold text-slate-400 hover:text-stone-300">Forgot password?</a>
                    </div>
                  </div>
                  <div class="mt-2">
                    <input id="password" name="password" type="password" autocomplete="current-password" required class="block w-full rounded-md border-0 bg-white/5 py-1.5 text-white shadow-sm ring-1 ring-inset ring-white/10 focus:ring-2 focus:ring-inset focus:ring-stone-500 sm:text-sm sm:leading-6">
                  </div>
                </div>
          
                <div>
                  <button type="submit" class="flex w-full justify-center rounded-md bg-slate-500 px-3 py-1.5 text-sm font-semibold leading-6 text-white shadow-sm hover:bg-stone-400 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-stone-500">Sign Up</button>
                </div>
              </form>
          
              <p class="mt-10 text-center text-sm text-slate-400">
                Already a member?
                <a href="/login" class="font-semibold leading-6 text-slate-400 hover:text-stone-300">Sign in here</a>
              </p>
            </div>
             -->
            {/if}


