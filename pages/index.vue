<server lang="ts">
const message = "Hello World!!!";
const bye = "bye!";
export const GET = defineEventHandler(() => ({ message }));
export const POST = defineEventHandler(() => ({ message: bye }));
</server>

<script lang="ts" setup>
const { data } = await useFetch("/api/index");
async function func() {
  console.log(await $fetch("/api/index", { method: "POST" }));
}
</script>

<template>
  <div>
    <p>{{ data }}</p>
    <button @click="func">click</button>
  </div>
</template>
