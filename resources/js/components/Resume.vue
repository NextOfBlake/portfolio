<template>
    <div id="resume">
        <cover/>

        <div id="spacer"></div>

        <!--<div class="gid">-->
            <!--<div class="item" v-for="item in items">-->
                <!--{{ item }}-->
            <!--</div>-->
        <!--</div>-->

        <div class="container">
            <br>
            <card-list :cards="cards"/>
            <br>
        </div>

        <modal name="hello-world">
            helo, wold.
        </modal>

        <fab
                :main-icon="mainIcon"
                :position="position"
                :bg-color="bgColor"
                :actions="fabActions"
                @show="show"
                @hide="hide"
        ></fab>
    </div>
</template>

<script>
    import fab from 'vue-fab'
    import Journey from './Journey'
    import Skills from './Skills'
    import References from './References'
    import Applications from './Applications'

    export default {
        components: {
            fab
        },

        mounted()
        {
            let cover = document.getElementById('cover')
            let spacer = document.getElementById('spacer')

            spacer.style.height = `${cover.clientHeight}px`
        },

        data(){
            return {
                bgColor: '#35216a',
                position: 'bottom-right',
                mainIcon: 'menu',
                fabActions: [
                    {
                        name: 'show',
                        icon: 'email',
                        tooltip: 'hello wold'
                    },
                    {
                        name: 'hide',
                        icon: 'textsms'
                    },
                    {
                        name: 'book',
                        icon: 'calendar_today'
                    }
                ],
                items: [
                    'My Journey',
                    'Professional Skills',
                    'References',
                    'Certifications',
                    'Applications'
                ],
                cards: [
                    {
                        name: 'My Journey',
                        component: Journey
                    },
                    {
                        name: 'Professional Skills',
                        component: Skills
                    },
                    {
                        name: 'References & Recommendations',
                        component: References
                    },
                    {
                        name: 'Applications *not behind NDA*',
                        component: Applications
                    }
                ]
            }
        },
        methods: {
            show () {
                this.$modal.show('hello-world');
            },
            hide () {
                this.$modal.hide('hello-world');
            }
        }
    }
</script>

<style lang="scss">
    .spacer {

    }
</style>