<template>
    <div id="app">
        <div class="slider">
            <div class="slider__wrapper">
                <Slide
                    v-for="(slide, index) in slides"
                    v-if="index === currentSlide"
                    :src="slide.src"
                    :key="index"
                />
                <button class="slider__nav-leftside" type="button" @click="slideBack()">&lt;</button>
                <button class="slider__nav-rightside" type="button" @click="slideForward()">&gt;</button>
            </div>
        </div>
        <Paginator
            :slidesCount="slides.length"
            :clickHandler="toggleSlide"
            :currentSlide="currentSlide"
        />
    </div>
</template>

<script>
import Slide from './components/Slide.vue';
import Paginator from './components/Paginator.vue';

export default {
	name: 'app',
	components: {
		Slide,
		Paginator,
	},
	data() {
		return {
			currentSlide: 0,
			slides: [
				{
					src: require('@/assets/test-1.jpg'),
				},
				{
					src: require('@/assets/test-2.jpg'),
				},
				{
					src: require('@/assets/test-3.jpg'),
				},
			],
		};
	},
	methods: {
		toggleSlide(index) {
			this.currentSlide = index;
		},
		slideBack() {
			this.currentSlide === 0
				? (this.currentSlide = this.slides.length - 1)
				: --this.currentSlide;
		},
		slideForward() {
			this.currentSlide === this.slides.length - 1
				? (this.currentSlide = 0)
				: ++this.currentSlide;
		},
	},
};
</script>

<style lang="sass">
	.slider__wrapper
		position: relative
		width: 500px
		height: 400px

	.slider__nav-leftside
		position: absolute
		top: 50%
		left: 10px
		tranform: translateY(-50%)
		width: 30px
		height: 30px
	
	.slider__nav-rightside
		position: absolute
		top: 50%
		right: 10px
		tranform: translateY(-50%)
		width: 30px
		height: 30px
	
 
</style>
 