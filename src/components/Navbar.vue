<template>
    <div class="navbar navbar-dark bg-dark">
           <router-link :to="{ name: 'home'}" class="navbar-brand"> Formularios </router-link>
           <div class="d-flex">
            <router-link class="btn btn-dark" :to="{name:'about'}">Tareas</router-link>
           </div>
    </div>
</template>

 