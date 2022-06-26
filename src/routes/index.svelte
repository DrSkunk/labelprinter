<script>
	let labels = new Array(5 * 13).fill(0).map((_, i) => i);
	const rows = labels.reduce((acc, label, i) => {
		if (i % 5 === 0) {
			acc.push([]);
		}
		acc[acc.length - 1].push(label);
		return acc;
	}, []);
	console.log(rows);
</script>

<!-- <div class="w-[210mm] h-[297mm] inline-flex items-start justify-center bg-slate-200">
	<div class="w-[190mm] my-auto">
		{#each labels as label}
			<div class="w-[38mm] h-[21.2mm] border bg-slate-50 inline-flex items-center justify-center">
				{label}
			</div>
		{/each}
	</div>
</div> -->

<button class="print:hidden border px-4 py-2 bg-blue-100 block" on:click={() => window.print()}
	>Print</button
>

<div class="w-[210mm] h-[297mm] inline-flex items-start justify-center bg-slate-200">
	<table class="mx-auto my-auto border-collapse">
		{#each rows as row}
			<tr>
				{#each row as label}
					<td
						class="w-[38mm] h-[21.2mm] border border-black bg-slate-50 inline-flex items-center justify-center"
					>
						{label}
					</td>
				{/each}
			</tr>
		{/each}
	</table>
</div>
