<template>
    <div v-if="messageUpload" class="flex items-center gap-3 mt-1">
        <div v-if="messageUpload.channel_message_upload_type_name === 'Image'" class="w-full bg-gray-800 rounded-md overflow-hidden">
            <img :src="messageUpload.room_file.src" class="w-full h-full object-cover" />
        </div>
        <div v-if="messageUpload.channel_message_upload_type_name === 'Video'" class="w-full bg-gray-800 rounded-md overflow-hidden">
            <video :src="messageUpload.room_file.src" class="w-full h-full object-cover" controls />
        </div>
        <div v-if="messageUpload.channel_message_upload_type_name === 'Document'"
            class="w-full p-3 bg-indigo-500 hover:bg-indigo-700 rounded-md overflow-hidden flex items-center justify-start gap-3">
            <!--!Font Awesome Free 6.6.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
            <svg xmlns="http://www.w3.org/2000/svg" width="36" fill="white" viewBox="0 0 512 512">
                <path
                    d="M288 32c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 242.7-73.4-73.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3l128 128c12.5 12.5 32.8 12.5 45.3 0l128-128c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L288 274.7 288 32zM64 352c-35.3 0-64 28.7-64 64l0 32c0 35.3 28.7 64 64 64l384 0c35.3 0 64-28.7 64-64l0-32c0-35.3-28.7-64-64-64l-101.5 0-45.3 45.3c-25 25-65.5 25-90.5 0L165.5 352 64 352zm368 56a24 24 0 1 1 0 48 24 24 0 1 1 0-48z" />
            </svg>
            <a :href="messageUpload.room_file.src" target="_blank" class="text-white">
                {{ messageUpload.room_file.src }}
            </a>
        </div>
    </div>
</template>

<script setup lang="ts">
defineProps({
    messageUpload: {
        type: Object,
        required: false
    }
})
</script>