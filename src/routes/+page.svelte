<script lang="ts">
import TodoItem from "$lib/components/TodoItem.svelte";
    const todos = $state([{ todo: "Cleaning", deadline: new Date('2/23/2025')}])
    let showAddTodo = $state(false)
    let todoText = $state("")
    let dateText = $state(new Date())

    function addTodo(){
        todos.push({todo: todoText, deadline: dateText});
        todoText = ''
        dateText = new Date()
    }

    function showAddTodoFunction(){
        showAddTodo = !showAddTodo
    }
</script>

<div>
    <div>
        <button onclick={showAddTodoFunction}>Add todo</button>
    </div>
{#if showAddTodo}
	<div>
        <input bind:value={todoText} type="text">
        <input bind:value={dateText} type="date" name="" id="">
        <button onclick={addTodo}>Add</button>
    </div>
{/if}
{#each todos as todo (todo)}
    <TodoItem todo={todo.todo} deadline={todo.deadline}/>
{/each}
</div>


