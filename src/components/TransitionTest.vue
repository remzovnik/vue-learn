<template>
    <div>
        <button class="toggler" type="button" @click="isShown = !isShown">Toggle</button>
        <transition name="show">
            <div class="block" v-show="isShown"></div>
        </transition>
    </div>
</template>

<script>
export default {
	name: 'TransitionTest',
	data() {
		return {
			isShown: false,
		};
	},
};
</script>

<style scoped>
.block {
	background: gold;
}

.show-enter-active {
	transition: opacity 1s, transform 1s;
}

.show-leave-active {
	transition: opacity 1s, transform 1s;
}

.show-enter,
.show-leave-to {
	opacity: 0;
	transform: translateY(0);
}

.show-enter-to,
.show-leave {
	opacity: 1;
	transform: translateY(200px);
}
</style>
