<template>
<q-layout view="lHh Lpr lFf">
    <q-layout-header>
        <q-btn class="menu" size="md" flat @click="toggleMenu()">
            <q-icon name="menu" />
        </q-btn>

        <q-toolbar-title>
            <div class="q-mt-sm">
                <img src="statics/ryo-wallet.svg" height="32">
                <span>solo mining</span>
            </div>
        </q-toolbar-title>

    </q-layout-header>

    <q-layout-drawer v-model="menuOpen">
        <q-list no-border link inset-delimiter>
            <q-item v-ripple to="/dashboard">
                <q-item-side icon="dashboard" />
                <q-item-main label="Dashboard" sublabel="Global solo miner stats" />
            </q-item>
            <q-item v-ripple to="/worker-stats">
                <q-item-side icon="person" />
                <q-item-main label="Worker Statistics" sublabel="Individual miner stats" />
            </q-item>
            <q-item v-ripple to="/blocks">
                <q-item-side icon="apps" />
                <q-item-main label="Blocks" sublabel="Solo mined blocks" />
            </q-item>
            <q-item v-ripple to="/getting-started">
                <q-item-side icon="extension" />
                <q-item-main label="Getting Started" sublabel="How to solo mine" />
            </q-item>
        </q-list>
    </q-layout-drawer>

    <q-page-container>
        <router-view />
    </q-page-container>
</q-layout>
</template>

<script>
import { openURL } from "quasar"

export default {
    data () {
        return {
            menuOpen: this.$q.platform.is.desktop
        }
    },
    methods: {
        toggleMenu() {
            this.menuOpen = !this.menuOpen
        },
        openURL
    }
}
</script>

<style>
</style>
