<script>
  import { fade } from "svelte/transition";

  export let auth;

  let mode = "signIn";
  let email = "";
  let password = "";
  let errorMsg = "";

  $: title = mode === "signIn" ? "Welcome Back!" : "Register";

  async function handleSubmit() {
    try {
      if (mode === "signIn") {
      }
    } catch (error) {
      errorMsg = error.message;
    }
  }
</script>

<div class="container mx-auto">
  <div class="flex justify-center px-6 my-12">
    <!-- Row -->
    <div class="w-full xl:w-3/4 lg:w-11/12 flex">
            <!-- Col -->
            <div
                class="w-full h-auto bg-gray-400 hidden lg:block lg:w-1/2 bg-cover rounded-l-lg"
                style="background-image: url('https://source.unsplash.com/K4mSJ7kc0As/600x800')"
            ></div>
            <!-- Col -->
            <div class="w-full lg:w-1/2 bg-white p-5 rounded-lg lg:rounded-l-none">
                {#key mode}
                <div in:fade>
                <h3 class="pt-4 text-2xl text-center">{title}</h3>
                <form on:submit|preventDefault={handleSubmit} class="px-8 pt-6 pb-8 mb-4 bg-white rounded">
                    <div class="mb-4">
                        <label class="block mb-2 text-sm font-bold text-gray-700" for="email">
                            Email
                        </label>
                        <input
                        bind:value={email}
                            class="w-full px-3 py-2 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
                            id="email"
                            type="email"
                            placeholder="Email"
                        />
                    </div>
                    <div class="mb-4">
                        <label class="block mb-2 text-sm font-bold text-gray-700" for="password">
                            Password
                        </label>
                        <input
                        bind:value={password}
                            class="w-full px-3 py-2 mb-3 text-sm leading-tight text-gray-700 border rounded shadow appearance-none focus:outline-none focus:shadow-outline"
                            id="password"
                            type="password"
                            placeholder="******************"
                        />
                      
                    </div>
                    <div class="mb-4">
                       <p class="text-red-500">{errorMsg}</p>
                    </div>
                    {#if mode === 'signIn'}
                    <div class="mb-6 text-center">

                        <button
                            class="w-full px-4 py-2 font-bold text-white bg-blue-500 rounded-full hover:bg-blue-700 focus:outline-none focus:shadow-outline"
                            type="button"
                        >
                            Sign In
                        </button>
                    </div>
                    <hr class="mb-6 border-t" />
                    <div class="text-center">
                        <button
                        on:click={() => mode = 'signUp'}
                            class="inline-block text-sm text-blue-500 align-baseline hover:text-blue-800"
                          
                        >
                            Create an Account!
                    </button>
                    </div>
                    {:else}
                    <div class="mb-6 text-center">

                        <button
                            class="w-full px-4 py-2 font-bold text-white bg-blue-500 rounded-full hover:bg-blue-700 focus:outline-none focus:shadow-outline"
                            type="button"
                        >
                            Sign Up
                        </button>
                    </div>
                    <hr class="mb-6 border-t" />
                    <div class="text-center">
                        <button
                        on:click={() => mode = 'signIn'}
                            class="inline-block text-sm text-blue-500 align-baseline hover:text-blue-800"
                     
                        >
                            Log in
                    </button>
                    </div>
                    {/if}
                </form>
            </div>
                {/key}
               
            </div>
        </div>
  </div>
</div>
