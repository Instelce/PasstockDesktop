<script>
	import { writeTextFile, BaseDirectory } from '@tauri-apps/api/fs';
	// import { writeJsonFile } from 'write-json-file';

	import Topbar from "../components/Topbar.svelte";
	import Button from "../components/Button.svelte";

	import passwords from '../data.js';

	let data = JSON.stringify(passwords)

	let name;
	let email;
	let password;

	function createPassword () {
		let newData = data['password']

		newData.put('name', {name})
		newData.put('email', {email})
		newData.put('password', {password})

		console.log(newData);

		// writeJsonFile('../../data/passwords.json', newData)
	}
</script>

<Topbar>
  <Button to="/">
    Back
  </Button>
</Topbar>

<div class="container center">
	<form action="">
		<h2>New password</h2>

		<input type="text" placeholder="Name" bind:value="{name}">
		<input type="email" placeholder="Email" bind:value="{email}">
		<input type="text" placeholder="Password" bind:value="{password}">

		<p>{name}</p>

		<Button to="/" callback={createPassword}>
			Create
		</Button>
	</form>
</div>

<style>
	
</style>