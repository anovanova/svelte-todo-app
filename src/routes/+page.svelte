<script lang="ts">
import TodoItem from "$lib/components/TodoItem.svelte";
    const todos = [{ todo: "Cleaning", deadline: new Date('2/23/2025')}]
</script>

<div>
{#each todos as todo (todo)}
    <TodoItem todo={todo.todo} deadline={todo.deadline}/>
{/each}
</div>


