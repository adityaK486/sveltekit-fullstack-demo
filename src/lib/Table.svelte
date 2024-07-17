<script>
    export let names
</script>

<div
	class="mt-10 pt-10 w-full max-w-xl p-12 mx-auto rounded-lg shadow-xl dark:bg-white/10 bg-white/30 ring-1 ring-gray-900/5 backdrop-blur-lg"
>
	<div class="flex items-center justify-between mb-4">
		<div class="space-y-1">
			<h2 class="text-xl font-semibold">List of Users</h2>
			<p class="text-sm text-gray-500">
				Fetched {names.length} users
			</p>
		</div>
	</div>
	<div class="divide-y divide-gray-900/5">
		{#each names as user (user.id)}
			<div class="flex items-center justify-between py-3">
				<div class="flex items-center space-x-4">
					<div class="flex">
						<p class="font-medium pt-1 leading-none">{user.name}</p>
						<p class="font-medium pl-5 text-gray-500 pt-0">{user.email}</p>                        
					</div>
				</div>		
				<form method="POST" action="/profiles?/delete">
				<input type="hidden" name="id" id="id" value={user.id}>
				<button type="submit">
					<img class="w-4 float-right" src="./trash-can.svg" alt="delete"/>
				</button>
				</form>
			</div>
			<form method="POST" action="/profiles?/update">
			<input type="hidden" name="id" id="id" value={user.id}>
			<div class="flex h-10 gap-10">
				<input
          			class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
          			id="uname"
          			type="text"
          			placeholder="Update name"
          			name="uname"
        		/>
				<input
          			class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white focus:border-gray-500"
          			id="uemail"
          			type="text"
          			placeholder="Update email"
          			name="uemail"
        		/>
				<button
					type="submit"
					class="bg-yellow-500 hover:bg-blue-700 text-white font-bold px-2 rounded "
		  		>
					Update
		  		</button>
			</div>
			</form>
		{/each}
	</div>
</div>








<!-- <form method="POST" action="/profiles?/update">
	<input type="hidden" name="id" id="id" value={user.id}>
	<button type="submit">
		<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
			<path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75a4.5 4.5 0 0 1-4.884 4.484c-1.076-.091-2.264.071-2.95.904l-7.152 8.684a2.548 2.548 0 1 1-3.586-3.586l8.684-7.152c.833-.686.995-1.874.904-2.95a4.5 4.5 0 0 1 6.336-4.486l-3.276 3.276a3.004 3.004 0 0 0 2.25 2.25l3.276-3.276c.256.565.398 1.192.398 1.852Z" />
			<path stroke-linecap="round" stroke-linejoin="round" d="M4.867 19.125h.008v.008h-.008v-.008Z" />
		</svg>  
	</button>
	</form> -->