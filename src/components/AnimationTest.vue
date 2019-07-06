<template>
    <div>
        <button class="toggler" type="button" @click="isShown = !isShown">Toggle</button>
        <transition name="show" @enter="enter">
            <div class="block" v-show="isShown"></div>
        </transition>
    </div>
</template>

<script>
export default {
	name: 'AnimationTest',
	data() {
		return {
			isShown: false,
		};
	},
	methods: {
		enter() {
			console.log('element has appeared');
		},
	},
};
</script>

<style scoped>
.block {
	background: gold;
}

.show-enter {
	opacity: 0;
}

.show-leave-to {
	animation: bounce-in 1s ease-out;
}

.show-enter-to,
.show-leave {
	animation: bounce-in 1s ease-out reverse;
}

@keyframes bounce-in {
	0% {
		transform: skewX(10deg) translate(0, 0);
	}
	50% {
		transform: skewX(-10deg) translate(-100px, 200px);
		opacity: 1;
	}
	100% {
		transform: skewX(10deg) translate(100px, 400px);
		opacity: 0;
	}
}
</style>
