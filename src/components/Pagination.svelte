<script>
	export let totalCount;
	export let currentPageNumber;
	// @ts-ignore
	let x = currentPageNumber - 1;
	let from = x * 20;
	let to = x * 20 + 20;
</script>

<div class="bg-white px-4 py-3 flex items-center justify-between border-t border-gray-200 sm:px-6">
	<div class="hidden sm:flex-1 sm:flex sm:items-center sm:justify-between">
		<!-- <div>
			<p class="text-sm text-gray-700">
				Showing
				<span class="font-medium">{from}</span>
				to
				<span class="font-medium">{to}</span>
				of
				<span class="font-medium">{totalCount}</span>
				results
			</p>
		</div> -->
		<div class="w-full text-center">
			<nav
				class="relative z-0 inline-flex rounded-md shadow-sm -space-x-px"
				aria-label="Pagination"
			>
				<a
					href={`/pages/${currentPageNumber === 1 ? 1 : currentPageNumber - 1}`}
					class="relative inline-flex items-center px-2 py-2 rounded-l-md border border-gray-300 bg-white text-sm font-medium text-gray-500 hover:bg-gray-50"
				>
					<span class="sr-only">Previous</span>
					<!-- Heroicon name: solid/chevron-left -->
					<svg
						class="h-5 w-5"
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 20 20"
						fill="currentColor"
						aria-hidden="true"
					>
						<path
							fill-rule="evenodd"
							d="M12.707 5.293a1 1 0 010 1.414L9.414 10l3.293 3.293a1 1 0 01-1.414 1.414l-4-4a1 1 0 010-1.414l4-4a1 1 0 011.414 0z"
							clip-rule="evenodd"
						/>
					</svg>
				</a>
				<!-- Current: "z-10 bg-indigo-50 border-indigo-500 text-indigo-600", Default: "bg-white border-gray-300 text-gray-500 hover:bg-gray-50" -->
				<a
					href={`/pages/${currentPageNumber}`}
					aria-current="page"
					class="z-10 bg-indigo-50 border-indigo-500 text-indigo-600 relative inline-flex items-center px-4 py-2 border text-sm font-medium"
				>
					{currentPageNumber}
				</a>
				<a
					href={`/pages/${currentPageNumber + 1}`}
					class="bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-4 py-2 border text-sm font-medium"
				>
					{currentPageNumber + 1}
				</a>
				<a
					href={`/pages/${currentPageNumber + 2}`}
					class="bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-4 py-2 border text-sm font-medium"
				>
					{currentPageNumber + 2}
				</a>
				<span
					class="relative inline-flex items-center px-4 py-2 border border-gray-300 bg-white text-sm font-medium text-gray-700"
				>
					...
				</span>
				<a
					href={`/pages/${totalCount - 2}`}
					class="bg-white border-gray-300 text-gray-500 hover:bg-gray-50 hidden md:inline-flex relative items-center px-4 py-2 border text-sm font-medium"
				>
					{totalCount - 2}
				</a>
				<a
					href={`/pages/${currentPageNumber - 1}`}
					class="bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-4 py-2 border text-sm font-medium"
				>
					{totalCount - 1}
				</a>
				<a
					href={`/pages/${totalCount - 1}`}
					class="bg-white border-gray-300 text-gray-500 hover:bg-gray-50 relative inline-flex items-center px-4 py-2 border text-sm font-medium"
				>
					{totalCount}
				</a>
				<a
					href={`/pages/${currentPageNumber === totalCount ? totalCount : currentPageNumber + 1}`}
					class="relative inline-flex items-center px-2 py-2 rounded-r-md border border-gray-300 bg-white text-sm font-medium text-gray-500 hover:bg-gray-50"
				>
					<span class="sr-only">Next</span>
					<!-- Heroicon name: solid/chevron-right -->
					<svg
						class="h-5 w-5"
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 20 20"
						fill="currentColor"
						aria-hidden="true"
					>
						<path
							fill-rule="evenodd"
							d="M7.293 14.707a1 1 0 010-1.414L10.586 10 7.293 6.707a1 1 0 011.414-1.414l4 4a1 1 0 010 1.414l-4 4a1 1 0 01-1.414 0z"
							clip-rule="evenodd"
						/>
					</svg>
				</a>
			</nav>
		</div>
	</div>
</div>
