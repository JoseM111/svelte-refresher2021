<!-- ━━━━━━━━━ JS | TS ━━━━━━━━━ -->
<script lang="ts">
	import type { Contact } from './types/types'
	import ContactCard from './components/ContactCard.svelte'
	/** #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
	
	/**: - ©MEMBER-PROPERTIES| */
	/*| #™━━━━━━━━━━━━━━━━━━━━━|*/
	let name: string = ''
	let jobTitle: string = ''
	let imageURL: string = ''
	let description: string = ''
	let formState: string = 'empty'
	// let age: number = 38
	let createdContacts: Contact[] = []
	/*| #™━━━━━━━━━━━━━━━━━━━━━|*/
	
	/**| ™- LABELED-STATEMENT |*/
	/* #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
	// $: uppercaseName = name.toUpperCase()
	// $: console.log(`Name: ${ name }`)
	// $: name === 'J-Sin' ? age = 26 : null
	/* #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
	
	/** #™━━━━━━━━━━━━━━━━━━━ FUNCTION ━━━━━━━━━━━━━━━━━━━ */
		
		// const incrementCount = (): number => age += 1
		// END-OF: incrementCount--
	
	const addContact = () => {
			//..........
			// name.trim().length == 0
			// || jobTitle.trim().length == 0
			// || imageURL.trim().length == 0
			// || description.trim().length == 0
			// 	? formState = 'invalid'
			// 	: formState = 'isDone'
			
			if (
				name.trim().length == 0
				|| jobTitle.trim().length == 0
				|| imageURL.trim().length == 0
				|| description.trim().length == 0
			) {
				formState = 'invalid'
				return
			}
			
			createdContacts = [
				...createdContacts, {
					name: name,
					jobTitle: jobTitle,
					imageURL: imageURL,
					description: description,
				} ]
			
			formState = 'isDone'
			
		}
	// END-OF: addContact--
	
	// const changeName = (): string => name = 'J-Sin'
	// END-OF: changeName--
	
	// const inputHandler = (event: InputTargetEvent): void => {
	// 	//..........
	// 	name = event.target.value
	// }
	// // END-OF: inputHandler--

</script>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->

<div class="AppContainer">
	<!-- ━━━━━━━━━━━━━━━ CONTAINER ━━━━━━━━━━━━━━━ -->
	
	<main>
		
		<!--		&lt;!&ndash;⌨⌨⌨⌨|TITLE|⌨⌨⌨⌨&ndash;&gt;-->
		<!--		<h1>Hola {uppercaseName}. My age is {age}!</h1>-->
		<!--		-->
		<!--		<button on:click={incrementCount}>-->
		<!--			Change Age-->
		<!--		</button>-->
		
		<!--		<button class="chg-name-btn" on:click={changeName}-->
		<!--		>Change Name</button>-->
		<form class="form-control">
			
			<!--♠♠♠| Name-input |♠♠♠-->
			<label for="userName">User Name</label>
			<input
				id="userName"
				bind:value={name}
				placeholder="enter name"
				type="text"
			>
			
			<!--♠♠♠| jobTitle |♠♠♠-->
			<input
				bind:value={jobTitle}
				placeholder="enter job title"
				type="text"
			>
			
			<!--♠♠♠| Image |♠♠♠-->
			<input
				class="img-url"
				bind:value={imageURL}
				placeholder="enter image url"
				type="text"
			>
			
			<!--♠♠♠| description |♠♠♠-->
			<div class="textarea-desc">
				<textarea rows="3" bind:value={description} placeholder="enter description"></textarea>
			</div>
			
			<!-- Shortcut to the below with two way binding -->
			<!------------------------------------------------>
			<!--			<input-->
			<!--				on:input={inputHandler}-->
			<!--				placeholder="enter name"-->
			<!--				type="text"-->
			<!--				value={name}-->
			<!--			>-->
			<!------------------------------------------------>
		</form>
		
		<!--♠♠♠| Button(Add Contact) |♠♠♠-->
		<button
			class="addContactBtn"
			on:click={addContact}
		>Add Contact
		</button>
		
		<!--♠♠♠| ContactCard |♠♠♠-->
		<!---->
		{#if formState === 'invalid'}
			<p><b>Invalid Input</b></p>
			<!---->
		{:else}
			<p>
				<i>Please enter information a then press the
					<span class="addContactColor"><b>Add Contact</b></span> button.
				</i>
			</p>
		{/if}
		<!---->
		
		<!---->
		<ul>
			{#each createdContacts as contact, index}
				<li>
					<span class="span-align">
						<span class="indexColor">{index + 1}-</span>
						<span class="ContactCardPad">
							<ContactCard
								userName={contact.name}
								jobTitle={contact.jobTitle}
								description={contact.description}
								userImage={contact.imageURL}
							/>
						</span>
					</span>
				</li>
			{/each}
		</ul>
		
		<!---->
		<!--♠♠♠| ContactCard |♠♠♠-->
	
	</main>
	
	<!-- ━━━━━━━━━━━━━━━ CONTAINER ━━━━━━━━━━━━━━━ -->
</div>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->

<!-- ━━━━━━━━━ CSS | SCSS | SASS ━━━━━━━━━ -->
<style lang="scss">
	@import 'public/styles/app.scss';
	@import 'public/styles/global.scss';
	
	input {
		margin-top: 10px;
	}
</style>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->
