<template>
    <div class="conditional-rendering container">
        <div class="row">
            <div class="col-12">
                <h1>Conditional Rendering</h1>
                <h5>Using The v-if Directive With A Direct Value</h5>
                <p>We can use conditional rendering to only draw blocks of code to the screen if the condition is true.
                    This is done by attaching the v-if directive to the element. You can either supply a direct boolean
                    value, or an expression that will evaluate to one.</p>
                <pre>
                    <code class="language-html">
                        <div class="player-card" v-if="true">
                            <div>
                                <img :src="player.photo" />
                            </div>
                            <div>
                                <span>{{player.name}}</span>
                            </div>
                            <div>
                                <span>{{player.position}}</span>
                            </div>
                            <div>
                                <span>{{player.number}}</span>
                            </div>
                        </div>
                    </code>
                </pre>
                <p>We directly supplied a value of true to the v-if directive of the "player-card" element and so it
                    will be rendered to the screen.</p>
                <h5>Using The v-if Directive With A Referenced Value</h5>
                <pre>
                    <code class="language-html">
                        <div class="player-card" v-if="showPlayer">
                            <div>
                                <img :src="player.photo" />
                            </div>
                            <div>
                                <span>{{player.name}}</span>
                            </div>
                            <div>
                                <span>{{player.position}}</span>
                            </div>
                            <div>
                                <span>{{player.number}}</span>
                            </div>
                        </div>
                    </code>
                </pre>
                <pre>
                    <code class="language-javascript">
                        export default {
                            data() {
                                return {
                                    showPlayer: true,
                                    player: {
                                        photo: "https://robohash.org/D$",
                                        name: "D$",
                                        position: "WR",
                                        number: 4
                                    }
                                }
                            }
                        }
                    </code>
                </pre>
                <p>In this case we are using a referenced value from the components data to determine wether or not to
                    display the "player-card" element.</p>
                <h5>Using The v-if, v-else-if, And v-else Directives</h5>
                <p>Just like in regular javascript conditionals, we can use if, else if, and else statements. It will
                    look something like:</p>
                <pre>
                    <code class="language-html">
                        <div v-if="num === 1">
                        <p>The Number is 1.</p>
                        </div>
                        <div v-else-if="num === 2">
                        <p>The Number is 2.</p>
                        </div>
                        <div v-else-if="num === 3">
                        <p>The Number is 3.</p>
                        </div>
                        <div v-else>
                        <p>The Number is not 1, 2, or 3.</p>
                        </div>
                    </code>
                </pre>
                <p>If the value of num is 1, we will get "The Number is 1." rendered to the screen. Using the v-else-if
                    and v-else directives is going to ensure only one of the above elements is displayed at any time.
                    If you want multiple elements displayed depending on different conditions, you can use multiple
                    v-if directives at the same time.</p>
                <h5>Using The v-show Directive</h5>
                <p>One other way we can use conditional rendering is the v-show directive. The difference between v-if
                    and v-show is that v-if will not render the element to the page in any way. Using v-show means that
                    the element will always be rendered on the page(takes up space) but the condition of the v-show
                    will toggle the display CSS property on the element. In other words, it will always be there, but
                    may not be visible.</p>
                <p>Just like the v-if directive, v-show can accept a direct boolean value, or a conditional from our
                    javascript in the component.</p>
                <pre>
                    <code class="language-html">
                        <div class="player-card" v-show="true">
                            <div>
                                <img :src="player.photo" />
                            </div>
                            <div>
                                <span>{{player.name}}</span>
                            </div>
                            <div>
                                <span>{{player.position}}</span>
                            </div>
                            <div>
                                <span>{{player.number}}</span>
                            </div>
                        </div>
                    </code>
                </pre>
            </div>
            <exercise></exercise>
        </div>
    </div>
</template>


<script>
    import Exercise from "../components/ConditionalRenderingExercise.vue"
    export default {
        name: 'conditional-rendering',
        data() {
            return {
                showPlayer: true,
                player: {
                    name: '{{ player.name }}',
                    position: '{{ player.position }}',
                    number: '{{ player.number }}'
                }
            }
        },
        computed: {},
        methods: {},
        components: { Exercise }
    }
</script>


<style scoped>

</style>