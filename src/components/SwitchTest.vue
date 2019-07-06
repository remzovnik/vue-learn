<template>
    <div>
        <button class="toggler" type="button" @click="switchBlocks()">Toggle</button>
        <transition name="show" mode="out-in">
            <div class="block block-1" v-if="currentBlock === 0" key="block-1"></div>
            <div class="block block-2" v-if="currentBlock === 1" key="block-2"></div>
            <div class="block block-3" v-if="currentBlock === 2" key="block-3"></div>
        </transition>
    </div>
</template>

<script>
export default {
	name: 'SwitchTest',
	data() {
		return {
			currentBlock: 0,
		};
	},
	methods: {
		switchBlocks() {
			this.currentBlock === 2
				? (this.currentBlock = 0)
				: ++this.currentBlock;
		},
	},
};
</script>

<style>
.block-1 {
	background: gold;
}

.block-2 {
	background: green;
}

.block-3 {
	background: saddlebrown;
}

.show-enter-active {
	transition: opacity 0.5s, transform 0.5s;
}

.show-leave-active {
	transition: opacity 0.5s, transform 0.5s;
}

.show-enter {
	opacity: 0;
	transform: translateY(100px);
}

.show-leave-to {
	opacity: 0;
	transform: translateX(-200px);
}

.show-enter-to {
	opacity: 1;
	transform: translateY(0);
}
</style>
