<!-- ━━━━━━━━━ JS | TS ━━━━━━━━━ -->
<script lang="ts">
    /** #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */

    /**: - ©MEMBER-PROPERTIES| */
    /*| #™━━━━━━━━━━━━━━━━━━━━━|*/
    export let name: string = ''
    export let jobTitle: string = ''
    export let imageURL: string = ''
    export let description: string = ''
    /*| #™━━━━━━━━━━━━━━━━━━━━━|*/

    /**| ™- LABELED-STATEMENT |*/
    /* #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */

    /* #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */

    /** #™━━━━━━━━━━━━━━━━━━━ FUNCTION ━━━━━━━━━━━━━━━━━━━ */



</script>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->

<div class="AppContainer">
	<!-- ━━━━━━━━━━━━━━━ CONTAINER ━━━━━━━━━━━━━━━ -->

	<main>
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


	</main>
  
  <!-- ━━━━━━━━━━━━━━━ CONTAINER ━━━━━━━━━━━━━━━ -->
</div>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->

<!-- ━━━━━━━━━ CSS | SCSS | SASS ━━━━━━━━━ -->
<style lang="scss">
	@import 'public/styles/FormInput.scss';
  @import 'public/styles/global.scss';
  
  input {
    margin-top: 10px;
  }
</style>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->
