<template>
    <ul class="paginator">
        <li v-for="(slideToggler, index) in slidesCount">
            <button
                class="paginator__item"
                :class="(currentSlide === index) ? 'active' : ''"
                type="button"
                @click="clickHandler(index)"
            ></button>
        </li>
    </ul>
</template>

<script>
export default {
	name: 'Paginator',
	props: {
		slidesCount: Number,
		clickHandler: Function,
		currentSlide: Number,
	},
};
</script>

<style lang="sass">
.paginator
	display: flex
	margin: 20px -10px 40px
	padding: 0
	list-style: none
	&__item
		width: 30px
		height: 30px
		margin: 0 10px
		border: 1px solid steelblue
		border-radius: 50%
		background-color: none	
		&:focus
			outline: none
		&.active
			background-color: steelblue
</style>