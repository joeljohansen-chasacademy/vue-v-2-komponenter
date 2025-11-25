<script setup>
import TodoItem from "./components/TodoItem.vue";
import UserCard from "./components/UserCard.vue";
import ProductCard from "./components/ProductCard.vue";
import TodoList from "./components/emits/TodoList.vue";

const product = {
	id: 1,
	name: "Vue.js Bok",
	price: 299,
};
</script>

<template>
	<div id="app">
		<h1>Vue.js Components - Demo</h1>
		<div class="example-card">
    <h2>Todo Item</h2>
			<TodoItem text="Köp mat" completed />
			<TodoItem text="Lägg till mat" />
		</div>
		<div class="example-card">
        <h2>User Card</h2>
				<UserCard
					name="Anna Andersson"
					:age="28"
					role="Admin"
				/>

				<!-- Med default values -->
				<UserCard name="Erik Eriksson" :age="35" />
		</div>
		<div class="example-card">
      <h2>Product Card</h2>
			<ProductCard
				:product="product"
				:tags="['Programmering', 'JavaScript', 'Frontend']"
				:in-stock="true"
			/>
		</div>
	</div>
  <div class="example-card">
    <h2>Todo List</h2>
    <TodoList />
  </div>
</template>

<style scoped>
#app {
	max-width: 800px;
	margin: 0 auto;
	padding: 20px;
}

h1 {
	text-align: center;
	margin-bottom: 30px;
}
</style>
