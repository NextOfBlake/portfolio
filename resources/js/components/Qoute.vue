<template>
        <div class="panel panel-default">
            <div class="panel-body quote">
                <slot></slot>
            </div>
        </div>
</template>

<script>

</script>

<style>
    .panel-body{
        font-family: 'Arizonia', cursive;
        font-size: 20px;
        color: #6e6e6e;
    }
    .quote {
        cursor: pointer;
    }
</style>