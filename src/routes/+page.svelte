<script lang="ts">
	import type { project } from '$lib/utils.ts';
	import ProjectTile from '$lib/components/projectTile.svelte';
	import { GithubIcon, TwitterIcon } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button';

	const projects: project[] = [
		{
			name: 'chat_room',
			language: 'golang',
			description: 'A chat room application built with golang with postgresql as the database',
			tags: ['golang', 'postgresql', 'git', 'htmx', 'tailwindcss'],
			github: 'https://github.com/Ahdeyyy/chat_room',
			link: 'https://chat-room-qso9.onrender.com'
		},
		{
			name: 'go-cgpacalc',
			language: 'golang',
			description:
				"A command line application that calculates your CGPA based on unilags' grade system",
			tags: ['golang', 'charmcli', 'git'],
			github: 'https://github.com/Ahdeyyy/go-cgpacalc'
		},
		{
			name: 'MonkeyLangEditor',
			language: 'typescript',
			description:
				'A web based editor for the monkey programming language from the book "Writing an interpreter in go" by Thorsten Ball with the backend written in golang',
			tags: ['typescript', 'golang', 'git', 'svelte', 'tailwindcss'],
			github: 'https://github.com/Ahdeyyy/MonkeyLangEditor',
			link: 'https://monkey-lang-editor.vercel.app'
		},
		{
			name: 'Ledger',
			language: 'typescript',
			description:
				'A web based ledger application that allows you to keep track of your expenses and income',
			tags: ['typescript', 'git', 'svelte', 'tailwindcss'],
			github: 'https://github.com/Ahdeyyy/Ledger',
			link: 'https://ledger-eight.vercel.app'
		},
		{
			name: 'Lyceum',
			language: 'typescript',
			description:
				'A web based application that quizzes you on your knowledge of various unilag courses',
			tags: ['typescript', 'git', 'svelte', 'tailwindcss'],
			github: 'https://github.com/Ahdeyyy/lyceum',
			link: 'https://lyceum-plum.vercel.app'
		}
	];
</script>

<main class="relative lg:grid lg:grid-cols-12 overflow-x-clip scroll-smooth">
	<section
		class="top-0 left-0 grid h-screen col-span-3 mb-4 p-9 overflow-clip lg:p-7 place-content-center pattern-slate-950 lg:block pattern-opacity-100 pattern-bg-transparent pattern-size-6 pattern-moon lg:fixed"
	>
		<div class="relative grid grid-flow-row gap-4 p-4">
			<h2 class="text-5xl font-bold uppercase">Adeala Adebusuyi</h2>
			<p class="text-xl font-semibold">Fullstack developer</p>
			<p class="text-gray-400">I build frontend and backend applications.</p>
			<div class="flex gap-2 align-middle">
				<img
					src="adebusuyi.jpg"
					alt="adebusuyi"
					class="object-cover w-12 rounded-full aspect-square"
				/>
				<Button
					class="self-center"
					variant="link"
					href="https://github.com/Ahdeyyy"
					target="_blank"
				>
					<GithubIcon class="w-4 h-4 mr-1 fill-white" />
					<span>Github</span>
				</Button>
				<Button class="self-center" variant="link" href="https://x.com/ahdeyy21" target="_blank">
					<TwitterIcon class="w-4 h-4 mr-1 fill-white" />
					<span>Twitter</span>
				</Button>
			</div>

			<ul class="hidden p-5 capitalize list-disc lg:block">
				<li class="transition-all duration-500 hover:scale-105">
					<Button variant="link" href="/#projects">projects</Button>
				</li>
			</ul>
		</div>
	</section>

	<section
		class="static col-span-6 p-4 mb-4 lg:max-w-screen-md lg:p-8 overflow-x-clip scroll-smooth lg:absolute lg:w-fit lg:right-0"
		id="projects"
	>
		<div>
			<h2
				class="sticky top-0 z-40 w-screen p-5 text-lg font-medium tracking-widest uppercase lg:p-10 backdrop-blur-md"
			>
				projects
			</h2>
			<ul class="grid grid-flow-row p-4 gap-9">
				{#each projects as project}
					<li
						class="transition-all duration-75 odd:hover:rotate-1 even:hover:-rotate-1 hover:scale-105"
					>
						<ProjectTile {project} />
					</li>
				{/each}
			</ul>
		</div>
	</section>
</main>
