<!-- ━━━━━━━━━ JS | TS ━━━━━━━━━ -->
<script lang="ts">
	
	/**: - ©MEMBER-PROPERTIES| */
	/*| #™━━━━━━━━━━━━━━━━━━━━━|*/
	export let userName: string = "DEFAULT"
	export let jobTitle: string = "DEFAULT"
	export let userImage: string = ""
	export let description: string = "DEFAULT"
	/*| #™━━━━━━━━━━━━━━━━━━━━━|*/
	
	/**| ™- LABELED-STATEMENT |*/
	/* #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
	
	/* #™━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ */
	
	/** #™━━━━━━━━━━━━━━━━━━━ FUNCTION ━━━━━━━━━━━━━━━━━━━ */
</script>
<!-- ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->

<!-- ━━━━━━━━━ HTML  ━━━━━━━━━ -->
<div class="ContactCardContainer">
	<!-- ━━━━━━━━━━━━━━━ CONTAINER ━━━━━━━━━━━━━━━ -->
	
	<header>
		
		<div class={userImage ? 'img-container' : 'img-placeholder'}>
			<!--suppress HtmlUnknownTarget -->
			<img src={userImage} alt={userName}>
		</div>
		
		<div class="user-info">
			<h1>{userName}</h1>
			<h2>{jobTitle}</h2>
		</div>
		
	</header>
	
	<main>
		
		<!--⌨⌨⌨⌨|TITLE|⌨⌨⌨⌨-->
		<p class="description">{description}</p>	
	
	</main>
	
	<!-- ━━━━━━━━━━━━━━━ CONTAINER ━━━━━━━━━━━━━━━ -->
</div>
<!-- ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->

<!-- ━━━━━━━━━ CSS | SCSS | SASS ━━━━━━━━━ -->
<style lang="scss">
	@import 'public/styles/contact-card.scss';
	/* | ⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫ | */
	
	
	/* | ⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫ | */
	
	/* | ⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫⌫ | */
</style>
<!-- ⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️⚫️🔵🔵🔵🔵🔵🔵🔵🔵━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ -->