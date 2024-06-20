<template>
    <div>
        <SideBar>
            <NavBar />
            <DashBoard />
        </SideBar>
    </div>
</template>
<script setup>
import NavBar from './components/NavbarView.vue';
import SideBar from './components/SidebarView.vue';
import DashBoard from '@/components/DashBoard.vue';

</script>