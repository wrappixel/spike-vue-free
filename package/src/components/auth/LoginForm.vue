<script setup lang="ts">
import { ref } from 'vue';
const checkbox = ref(false);
</script>

<template>
    <div class="d-flex align-center text-center mb-6">
        <div class="text-h6 w-100 px-5 font-weight-regular auth-divider position-relative">
            <span class="bg-surface px-5 py-3 position-relative text-subtitle-1 text-grey100">Your Social Campaigns</span>
        </div>
    </div>
    <div>
        <v-row class="mb-3">
            <v-col cols="12">
                <v-label class="font-weight-medium mb-1">Username</v-label>
                <v-text-field variant="outlined" class="pwdInput" hide-details color="primary"></v-text-field>
            </v-col>
            <v-col cols="12">
                <v-label class="font-weight-medium mb-1">Password</v-label>
                <v-text-field variant="outlined" class="border-borderColor" type="password" hide-details
                    color="primary"></v-text-field>
            </v-col>
            <v-col cols="12 " class="py-0">
                <div class="d-flex flex-wrap align-center w-100 ">
                    <v-checkbox hide-details color="primary">
                        <template v-slot:label class="">Remeber this Device</template>
                    </v-checkbox>
                    <div class="ml-sm-auto">
                        <RouterLink to=""
                            class="text-primary text-decoration-none text-body-1 opacity-1 font-weight-medium">
                            Forgot Password ?</RouterLink>
                    </div>
                </div>
            </v-col>
            <v-col cols="12">
                <v-btn size="large" rounded="pill" color="primary" class="rounded-pill" block type="submit" flat>Sign
                    In</v-btn>
            </v-col>
        </v-row>
    </div>
</template>
