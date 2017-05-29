<template>

    <div id="app">
        <div id="trigger-panel">
            <button v-on:click="trigger" id="trigger">show</button>
        </div>
        <div id="panel"></div>
    </div>

</template>


<script>
    import anime from 'animejs'

    export default {
        name: 'app',
        data () {
            return {
                show: true
            }
        },
        methods: {
            trigger: function() {
                if ( this.show ) {
                    anime({targets:'#panel', width: 400});
                }
                else {
                    anime({targets:'#panel', width: 0, easing: 'easeOutCirc'});
                }

                this.show = ! this.show;
            }
        }
    }
</script>


<style>
    #app {
        position: absolute;
        height: 100%;
        top: 0;
        overflow: hidden;
        border-right: 5px;
        right: 0;
    }

    #panel {
        height: inherit;
        width: 0px;
        display: inline-block;
        background-color: #c7c7c7;
        box-shadow: 0 0 10px rgba(0,0,0,0.5);
    }

    #trigger {
        float: right;
        position: absolute;
        bottom: 50px;
        margin-left: 30px;
    }

    #trigger-panel {
        height: inherit;
        width: 100px;
        display: inline-block;
    }
</style>
