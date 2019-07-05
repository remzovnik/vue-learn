<template>
    <div class="slide">
        <img class="slide__img" :src="src" alt />
    </div>
</template>

<script>
export default {
	name: 'Slide',
	props: {
		index: Number,
		src: String,
	},
};
</script>

<style lang="sass">
	.slide
		width: 100%
		height: 100%
	.slide__img
		width: 100%
		height: 100%	
		object-fit: cover
		user-select: none
		pointer-events: none
</style>