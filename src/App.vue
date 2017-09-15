<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Directives Exercise</h1>
                <!-- Exercise -->
                <!-- Build a Custom Directive which works like v-on (Listen for Events) -->
                <div class="form-group">
                        <label for="caps">Convert to Caps</label>
                        <input 
                                type="text"
                                id="caps"
                                class="form-control"
                                v-when:input="convertToCaps">
                    </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        directives: {
            'when': {
                bind(el, binding, vnode) {
                    el.addEventListener(binding.arg, binding.value);
                }
            }
        },
        methods: {
            convertToCaps(event) {
                event.target.value = event.target.value.toUpperCase();
            }
        }
    }
</script>

<style>
</style>
