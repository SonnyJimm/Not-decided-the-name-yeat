<template>
    <tr>
    <th scope="col">{{this.name}}</th>
    <th scope="col">{{this.age}}</th>
    <th scope="col">{{this.attemptedTime}}</th>
    <th scope="col">{{this.phone_number}}</th>
    <th scope="col">{{this.reason}}</th>
    </tr>
</template>
<script>
export default {
    name: "customerDetail",
    props: ["name","age","attemptedTime","phone_number","reason"]
}
</script>