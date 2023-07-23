<script setup>
    import { defineProps } from 'vue';

    const props = defineProps(['task', 'dateDeadline', 'timeDeadline', 'isDone', 'checkDone', 'deleteTask'])

</script>

<template>
    <div class="w-[18rem] m-3 p-4 inline relative border-white rounded-lg"
        :class="isDone ? 'bg-gray-700' : 'bg-gradient-to-r from-[#e944608a] to-[#A5D7E8]'"        
    >
        <h2 class="mb-2 text-xl text-[#090f1b] font-bold">{{props.task}}</h2>
        <p class="text-sm">Deadline: {{ props.dateDeadline }} {{ props.timeDeadline }}</p>
        <div @click="checkDone" class="absolute top-2.5 right-2.5">
            <svg v-if="isDone" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" style="fill: rgba(0, 0, 0, 1);transform: ;msFilter:;"><path d="M7 5c-1.103 0-2 .897-2 2v10c0 1.103.897 2 2 2h10c1.103 0 2-.897 2-2V7c0-1.103-.897-2-2-2H7zm0 12V7h10l.002 10H7z"></path><path d="M10.996 12.556 9.7 11.285l-1.4 1.43 2.704 2.647 4.699-4.651-1.406-1.422z"></path></svg>
            <svg v-else xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" style="fill: rgba(0, 0, 0, 1);transform: ;msFilter:;"><path d="M7 5c-1.103 0-2 .897-2 2v10c0 1.103.897 2 2 2h10c1.103 0 2-.897 2-2V7c0-1.103-.897-2-2-2H7zm0 12V7h10l.002 10H7z"></path></svg>
        </div>
        <svg @click="deleteTask" class="absolute bottom-2.5 right-2.5 hover:cursor-pointer" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" style="fill: rgb(116, 18, 18);transform: ;msFilter:;"><path d="M6 7H5v13a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V7H6zm4 12H8v-9h2v9zm6 0h-2v-9h2v9zm.618-15L15 2H9L7.382 4H3v2h18V4z"></path></svg>
    </div>
</template>