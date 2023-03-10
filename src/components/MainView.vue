<template>
    <nav class="navbar has-background-dark" role="navigation" aria-label="main navigation">
        <h4 class="title is-4 p-4 has-text-light">
            United Earth Team
        </h4>
    </nav>
    <div class="columns is-multiline is-tablet m-2">
        <div class="column is-half">
            <div class="box">
                <InstanceTag></InstanceTag>
            </div>
        </div>
        <div class="column is-half">
            <div class="box">
                <ServiceTag></ServiceTag>
            </div>
        </div>
        <div class="column is-half">
            <div class="box">
                <TagAvatar></TagAvatar>
            </div>
        </div>
        <div class="column is-half">
            <div class="box">
                <Readme></Readme>
            </div>
        </div>
    </div>

    <!-- <footer class="footer p-4">
        <div class="content has-text-centered">
            <p>
                Copyright © 2023 United Earth Team
            </p>
        </div>
    </footer> -->
</template>

<script setup>
import InstanceTag from './InstanceTag.vue'
import ServiceTag from './ServiceTag.vue'
import TagAvatar from './TagAvatar.vue'
import Readme from './Readme.vue'
</script>

<script>

</script>