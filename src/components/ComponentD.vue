<template>
<div>
  Component D
    {{username}}
</div>
</template>

<script>
export default {
  name: "ComponentD",
  inject: ['username']
};
</script>

<style lang="scss" scoped></style>
