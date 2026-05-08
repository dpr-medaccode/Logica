<script lang="ts">
	import { invoke } from "@tauri-apps/api/core";
	import Contador from "./../components/Contador.svelte";

	let greetMsg = $state("");

	async function greet(event: Event) {
		event.preventDefault();
		// Learn more about Tauri commands at https://tauri.app/develop/calling-rust/
		greetMsg = await invoke("greet", { name });
	}
</script>

<Contador />
