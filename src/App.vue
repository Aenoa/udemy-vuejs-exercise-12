<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1 v-myon:click="changeMyText">{{h1title}}</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        directives: {
            myon: {
                bind(el, binding, vnode) {
                    if(binding.arg == 'click') {
                        console.log('hi');
                        el.addEventListener('click', function(e) {
                            binding.value(e);
                        });
                    }
                }
            }
        },
        methods: {
            changeMyText() {
                this.h1title = "OH MY GOD STAHP CLICKIN MEEEEH";
            }
        },
        data() {
            return {
                h1title: "Directives Exercise",
            }
        }
    }
</script>

<style>
</style>
