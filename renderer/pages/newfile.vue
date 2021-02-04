<template>
    <div class = "random">
    <h1>{{ello}}</h1>
    </div>
</template>
<script>
export default {
    asyncData ({ req }) {
    return {
      ello: "ello"
    }
}
}
</script>