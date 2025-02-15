<template>
    <div>
        <h1 v-if="role === 'admin'">Admin Panel</h1>
        <h1 v-else>User Panel</h1>
    </div>
</template>

<script>
export default {
    data() {
        return {
            role: ''
        };
    },
    mounted() {
        axios.get('/api/user')
            .then(response => {
                this.role = response.data.role;
            });
    }
};
</script>
