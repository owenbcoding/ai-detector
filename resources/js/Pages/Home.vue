<template>
    <h1>AI Content Detection</h1>
    <div>
        <form @submit.prevent="submitForm">
            <textarea
                v-model="content"
                placeholder="Enter text or image URL"
            ></textarea>
            <select v-model="type">
                <option value="text">Text</option>
                <option value="image">Image</option>
            </select>
            <button type="submit">Analyze</button>
        </form>
        <div v-if="result">
            <p>Result: {{ result.type }}</p>
            <p>Confidence: {{ result.confidence }}%</p>
        </div>
    </div>
</template>

<!-- 
<script>
import { ref } from 'vue';
import { useForm } from '@inertiajs/inertia-vue3';

export default {
    setup() {
        const content = ref('');
        const type = ref('text');
        const result = ref(null);

        const submitForm = async () => {
            const response = await fetch('/detect', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                    'X-CSRF-TOKEN': document.querySelector('meta[name="csrf-token"]').content,
                },
                body: JSON.stringify({ content: content.value, type: type.value }),
            });

            if (response.ok) {
                result.value = await response.json();
            } else {
                console.error('Error analyzing content');
            }
        };

        return { content, type, submitForm, result };
    },
};
</script> -->
