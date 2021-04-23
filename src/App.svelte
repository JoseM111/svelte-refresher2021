<!-- ━━━━━━━━━ JS | TS ━━━━━━━━━ -->
<script lang="ts">
	import type {Contact} from './types/types'
  import ContactCard from './components/ContactCard.svelte'
  import FormInput from "./components/FormInput.svelte";
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
            id: Math.random(),
            name: name,
            jobTitle: jobTitle,
            imageURL: imageURL,
            description: description,
          }]
        
        formState = 'isDone'
  }
  // END-OF: addContact--
  
  const deleteFirstContact = () => {
    //..........
    createdContacts = createdContacts.slice(1)
  }
  // END-OF: deleteFirstContact =--
  
  const deleteLastContact = () => {
    //..........
    createdContacts = createdContacts.slice(0, -1)
  
  }
  // END-OF: deleteLastContact--
  
  
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
    
    <!-- FormInput-Component -->
        <FormInput
            bind:name={name}
            bind:jobTitle={jobTitle}
            bind:imageURL={imageURL}
            bind:description={description}
        />
    
    
    <!--♠♠♠| Button(Add Contact) |♠♠♠-->
		<button class="addContactBtn" on:click={addContact}
    >Add Contact
		</button>
    
    <!-----| Button(Delete First) |------->
    <div class="btnDelFirst">
      <button on:click={deleteFirstContact}>Delete First</button>
    </div>
    
    
    <!-----| Button(Delete Last) |------->
    <div class="btnDelLast">
      <button on:click={deleteLastContact}>Delete Last</button>
    </div>
    
    
    <!--♠♠♠| ContactCard |♠♠♠-->
    <!-- IF-STATEMENT -->
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
    
    <!-- FOR-EACH -->
    {#each createdContacts as contact, index (contact.id)}
        <h2><span class="indexColor">#{index + 1}</span></h2>
        <ContactCard
            userName={contact.name}
            jobTitle={contact.jobTitle}
            description={contact.description}
            userImage={contact.imageURL}
        />
    {:else}
      <p>
				Please add a <span class="addContactColor"><i>contact.</i></span>
				There are no contacts available currently.
			</p>
    {/each}
    
    <!---->
    <!--♠♠♠| ContactCard |♠♠♠-->

	</main>
  
  <!-- ━━━━━━━━━━━━━━━ CONTAINER ━━━━━━━━━━━━━━━ -->
</div>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->

<!-- ━━━━━━━━━ CSS | SCSS | SASS ━━━━━━━━━ -->
<style lang="scss">
	@import '../public/styles/App';
  @import 'public/styles/global.scss';
  
  input {
    margin-top: 10px;
  }
</style>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->
