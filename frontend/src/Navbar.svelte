<script>
    import { onMount } from 'svelte';

    onMount(() => {
        import('https://cdn.skypack.dev/tailwindcss/tailwind.min.css');
        import('https://unpkg.com/heroicons@1.0.4/dist/heroicons-sprite.js');
    });
</script>

<div class="navbar mt-[3%] h-[94%] w-16 md:w-44 fixed transition-all duration-200 ease-in-out ">

    <div class="navbar-header flex flex-col justify-center align-center items-center p-8">
        <div class="pb-4">
            <img src="https://pbs.twimg.com/profile_images/1605042959858036736/l8bFPAzw_400x400.jpg" class="rounded-full w-12">
        </div>

        <div class="text-md text-white font-bold">
            <p>Circus Toolkit</p>
        </div>

        <div class="text-sm text-gray-500 italic">
            v0.0.1
        </div>
    </div>

    <ul class="mt-10 space-y-6">
        <li class="px-6 py-2 transition-all duration-100 transform ">
            <a href="#" class="flex items-center space-x-2">
                <svg class="h-5 w-5 text-white" fill="none" stroke="currentColor">
                    <use xlink:href="#home"></use>
                </svg>
                <span class="text-white">Keybinds</span>
            </a>
        </li>
        <li class="px-6 py-2 transition-all duration-100 transform ">
            <a href="#" class="flex items-center space-x-2">
                <svg class="h-5 w-5 text-white" fill="none" stroke="currentColor">
                    <use xlink:href="#information-circle"></use>
                </svg>
                <span class="text-white">Review</span>
            </a>
        </li>
        <li class="px-6 py-2 transition-all duration-100 transform ">
            <a href="#" class="flex items-center space-x-2">
                <svg class="h-5 w-5 text-white" fill="none" stroke="currentColor">
                    <use xlink:href="#mail"></use>
                </svg>
                <span class="text-white">Github</span>
            </a>
        </li>
    </ul>
</div>

<style>
    .navbar {
        background-color: var(--bg-100);
        border-right: 1px solid var(--bg-300);
    }
    li:hover {
        background-color: var(--accent-100);
    }
</style>