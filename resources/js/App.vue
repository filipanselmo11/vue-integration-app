<template>
    <h1>
        VueSchool Rocks
    </h1>
    <router-view v-slot="{ Component, route  }">
        <div :key?="route.name">
            <Component :is="Component"/>
        </div>
    </router-view>
</template>
