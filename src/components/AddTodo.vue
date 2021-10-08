<template>
<form class="footer" @submit.prevent="addItem">
	<input placeholder="Add todo" class="input" v-model="title" />
	<button class="delete-todo" type="submit">Add</button>
</form>
</template>

<script lang="ts">
import {
	Component,
	Prop,
	Vue
} from 'vue-property-decorator';

@Component({
    components: {},
})
export default class AddTodo extends Vue {
    title: any;

    @Prop() idMax!: number;

    addItem() {
			const newItem = {
				id: this.idMax + 1,
				title: this.title,
				completed: false
			}
			this.$emit('add-todo', newItem)
    }
}
</script>

<style lang="css">
</style>
