<template>
<div class="todo-item flex">
	<div class="a flex">
		<input type="checkbox" :checked="todo.completed" @change="markItemCompleted" />
		<input type="text" :class="['todo-name', todo.completed ? 'completed' : '']" :value="todo.title"/>
	</div>
	<div>
		<button class="delete-todo" @click="updateItem" style="margin-right: 10px;">Update</button>
		<button class="delete-todo" @click="deleteItem">Delete</button>
	</div>
</div>
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
export default class TodoItem extends Vue {
	@Prop() todo!: Todo;
	title = '';

	markItemCompleted() {
		this.$emit('item-completed', this.$props.todo.id, this.$props.todo.title);
	}
	updateItem() {
		this.$emit('update-item', this.$props.todo.id, this.todo.title);
	}
	deleteItem = () => {
		this.$emit('delete-item', this.$props.todo.id)
	}
}
</script>

<style lang="css">
.todo-item {
	margin: 30px 0;
	justify-content: space-between;
	font-size: 20px;
}

.a {
	display: flex;
	align-items: center;
}

.a input:last-child {
	margin-right: 10px;
	width: 150px;
	border: none;
}

.flex {
	display: flex;
}

.completed {
	text-decoration: line-through;
}
</style>
