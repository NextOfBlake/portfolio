<template>
    <div id="cover">
        <div class="container-fluid">
            <div class="row">
                <div id='avatar' class="col-md-6">
                    <avatar username="Blake Higgs" src="http://blakehiggs.studio/images/profile.jpg" :size="avatarSize" :customStyle="customStyle"></avatar>
                </div>
                <div id='myqoute' class="col-md-6" style="margin: auto" v-if="!scrolled">
                    <qoute>
                            Start by doing what's necessary;
                            <br>
                            then do what's possible;
                            <br>
                            and suddenly you are doing the impossible
                    </qoute>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import GitHubBadge from 'vue-github-badge'
    import Avatar from 'vue-avatar'

    export default {
        components: {
            'github-badge': GitHubBadge,
            Avatar
        },

        created() {
            window.addEventListener('scroll', this.handleScroll);
        },

        data() {
            return {
                avatarSize: 200,
                customStyle: {
                    margin: 'auto',
                    borderWidth: '10px',
                    borderColor: '#007849',
                    borderStyle: 'double',
                    backgroundPosition: 'center'
                },
                iconSize: 25,
                scrolled: false,
            }
        },

        methods: {
            handleScroll()
            {
                this.scrolled = (window.scrollY > 0);
            }
        }
    }
</script>

<style lang="scss" scoped>
    #cover {
        position: fixed;
        background-color: #262228;
        width: 100vw;
        z-index: 100;
        
        .container-fluid {
            padding: 5vh;
        }
        
        h1 {
            text-align: center;
        }
        
        a:hover {
            color: white;
            text-decoration: #1b4b72;
        }
    }
</style>