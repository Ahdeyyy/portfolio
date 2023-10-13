<script lang="ts">
	import type { project } from '$lib/utils';
	import { Button } from '$lib/components/ui/button';
	import { Badge } from '$lib/components/ui/badge';
	import { Github } from 'lucide-svelte';

	export let project: project;
</script>

<div class="p-6 rounded-md shadow-lg bg-slate-900">
	<a target="__blank" href={project.link || project.github}>
		<div class="grid grid-flow-row gap-4">
			<p class="px-4 font-medium uppercase">
				{project.language}
			</p>

			<h3 class="px-4 text-xl font-semibold capitalize">{project.name}</h3>

			<p class="px-4 text-gray-400">{project.description}</p>
			<div class="grid justify-start grid-flow-col">
				<Button target="_blank" variant="link" href={project.github}>
					<Github class="w-4 h-4" />
					<span>
						{project.name}
					</span>
				</Button>

				<div class="flex flex-wrap gap-3">
					{#each project.tags as tag}
						<Badge class="p-2" variant="secondary">{tag}</Badge>
					{/each}
				</div>
			</div>
		</div>
	</a>
</div>
