<script lang="ts">
	import type { project } from '$lib/utils';
	import { Button } from '$lib/components/ui/button';
	import { Badge } from '$lib/components/ui/badge';
	import { Github } from 'lucide-svelte';

	export let project: project;
</script>

<div class="px-2 py-6 rounded-lg shadow-lg lg:rounded-md lg:p-8 bg-slate-900">
	<a target="__blank" href={project.link || project.github}>
		<div class="grid grid-flow-row gap-4 place-content-center">
			<p class="px-2 font-medium uppercase lg:px-8">
				{project.language}
			</p>

			<h3 class="px-2 text-lg font-semibold capitalize lg:text-xl lg:px-8">{project.name}</h3>

			<p class="px-2 text-gray-400 break-words md:text-lg lg:px-8">{project.description}</p>
			<div class="grid grid-flow-row lg:grid-flow-col">
				<a class="flex gap-1 px-3 mb-2 lg:px-8" target="_blank" href={project.github}>
					<Github class="w-4 aspect-square fill-white" />
					<span>
						{project.name}
					</span>
				</a>

				<div class="flex flex-wrap gap-2 px-3 lg:px-8 lg:gap-3">
					{#each project.tags as tag}
						<Badge class="p-2" variant="secondary">{tag}</Badge>
					{/each}
				</div>
			</div>
		</div>
	</a>
</div>
