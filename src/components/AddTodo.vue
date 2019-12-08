<template>
    <div class="input-form">
        <input type="text" name="title" placeholder="add todo...">
        <input type="submit" value="submit" class="button">
    </div>
</template>
<script>
export default {
    name: 'AddTodo'
}
</script>

<style scoped>
    .input-form{
        background: #333;
        color: #fff;
        text-align: center;
        padding: 10px;
    }
    .button{
        margin-left: 10px
    }
</style>