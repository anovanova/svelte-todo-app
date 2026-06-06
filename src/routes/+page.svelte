<script lang="ts">
import TodoItem from "$lib/components/TodoItem.svelte";
    const todos = $state([{ todo: "Cleaning", deadline: new Date('2/23/2025')}])
    let showAddTodo = $state(false)

    function addTodo(){
        todos.push();
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
        <input type="text">
        <input type="date" name="" id="">
        <button>Add</button>
    </div>
{/if}
{#each todos as todo (todo)}
    <TodoItem todo={todo.todo} deadline={todo.deadline}/>
{/each}
</div>


