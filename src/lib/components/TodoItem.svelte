<script lang="ts">
   const {todo, deadline} = $props()
</script>

<div>
    <div>
        <h4>{todo}</h4>
    </div>
    <div>
        <p>Deadline: <span>{new Date(deadline!).toLocaleDateString('en-GB')}</span></p>
    </div>
</div>