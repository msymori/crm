<script setup>
import { Link } from '@inertiajs/vue3';
import { ref } from 'vue'

const newTitle = ref('')
const newContent = ref('')
</script>

<template>
<div>
    Inertiaテスト <br>
    <a href="/">aタグ</a><br>
    <Link href="/">Link</Link><br>
    <Link :href="route('inertia.index')">名前付きルート</Link><br>
    <Link :href="route('inertia.show', { id: 1 })">ルートパラメータ</Link>
</div>

<div class="mb-8"></div>
<input type="text" name="newTitle" v-model="newTitle"><p>{{ newTitle }}</p><br>
<input type="text" name="newContent" v-model="newContent"><p>{{ newContent }}</p><br>

<Link as="button" method="post" :href="route('inertia.store')"
:data="{
    title: newTitle,
    content: newContent
}">送信</Link>
</template>