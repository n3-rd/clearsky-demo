<script lang="ts">
	import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
	import * as Sidebar from "$lib/components/ui/sidebar/index.js";
	import { useSidebar } from "$lib/components/ui/sidebar/index.js";
	import { Home, Users, ChartColumnBig, Smartphone, BookOpen, Settings } from "lucide-svelte";

	
	let items = [
		{ title: "Inbox", url: "/inbox", icon: Home },
		{ title: "Contacts", url: "/contacts", icon: Users },
		{ title: "Reports", url: "/reports", icon: ChartColumnBig },
		{ title: "Leadbox", url: "/leadbox", icon: Smartphone },
		{ title: "Leadform", url: "/leadform", icon: BookOpen },
		{ title: "Settings", url: "/settings", icon: Settings },
	];

	const sidebar = useSidebar();
</script>

<Sidebar.Group>
	<Sidebar.Menu>
		{#each items as mainItem (mainItem.title)}
			<Sidebar.MenuItem class="gap-4 !text-5xl">
				<Sidebar.MenuButton class="!py-7 flex items-center gap-3 pl-9 hover:text-primary font-medium">
					<mainItem.icon class="!w-6 !h-6" />
					{mainItem.title}
				</Sidebar.MenuButton>
			</Sidebar.MenuItem>
		{/each}
	</Sidebar.Menu>
</Sidebar.Group>
