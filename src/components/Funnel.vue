<template>
    <div>
        <b-card no-body>
            <b-tabs pills card vertical>
                <b-tab active title-link-class="custome__title">
                    <template v-slot:title>
                        <span>Rejected ({{candidates.filter(candidate => candidate.rejected).length}})</span>
                    </template>
                    <b-card-text>
                        <b-list-group>
                            <div v-for="candidate in candidates" v-bind:key="candidate.id">
                                <b-list-group-item v-if="candidate.rejected">
                                    <Candidate v-bind:candidate="candidate" />
                                </b-list-group-item>
                            </div>
                            <p v-if="!candidates.filter(candidate => candidate.rejected).length">No rejected candidates</p>
                        </b-list-group>
                    </b-card-text>
                </b-tab> 
                
                <b-tab title-link-class="custome__title">
                    <template v-slot:title>
                        <span>Saved ({{candidates.filter(candidate => candidate.saved).length}})</span>
                    </template>
                    <b-card-text>
                        <b-list-group>
                            <div v-for="candidate in candidates" v-bind:key="candidate.id">
                                <b-list-group-item v-if="candidate.saved">
                                    <Candidate v-bind:candidate="candidate" />
                                </b-list-group-item>
                            </div>
                            <p v-if="!candidates.filter(candidate => candidate.saved).length">No saved candidates</p>
                        </b-list-group>
                    </b-card-text>
                </b-tab>
                <b-tab title-link-class="custome__title" title="Selections"><b-card-text>Selections</b-card-text></b-tab>
                <b-tab title-link-class="custome__title" title="Backups"><b-card-text>Backups</b-card-text></b-tab>
                <b-tab title-link-class="custome__title" title="Recos"><b-card-text>Recos</b-card-text></b-tab>
            </b-tabs>
        </b-card>
    </div>
</template>

<script>
import Candidate from './Candidate.vue'

export default {
    name: "Funnel",
    components: {
        Candidate
    },
    props: ['candidates']
}
</script>

<style>
    .card {
        border: none;
    }

    .card-header {
        background-color: #ffffff;
    }

    .custome__title {
        position: relative;
        padding: 10px 10px 10px 20px;
    }

    .nav-item .custome__title::before {
        content: '';
        position: absolute;
        top: 50%;
        left: -10px;
        transform: translateY(-50%);
        height: 20px;
        width: 20px;
        background-color: #ffffff;
        border: 2px solid #666666;
        border-radius: 50%;
        z-index: 3;
    }

    .nav-pills .nav-item .custome__title.active {
        color: #666666;
        background-color: transparent;
    }

    .nav-item .custome__title.active::before {
        background-color: #ffffff;
        border: 2px solid #007bff;
    }

    .nav-item:not(:last-child) .custome__title::after {
        content: '';
        position: absolute;
        top: calc(50% + 12px);
        left: -1px;
        transform: translateY(-50%);
        height: 100%;
        width: 2px;
        background-color: #666666;
        z-index: 2;
    }
</style>