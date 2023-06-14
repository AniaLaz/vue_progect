<template>
    <div v-if="inVisible" > 
        <!-- v-if - по какому то условию, рендерить или не рендерить елемент -->
        <!-- v-show="false"  спрячит элемент, но оставит его в дереве -->

        <ul>
            <li v-for="fruit in fruits" :key="fruit">{{ fruit }}</li>
        </ul>
<h1>Directivees</h1>
    </div>
</template>

<script>
    export default {
    name: 'DirectiveesTest',
        data() {
            return {
                inVisible: true,
                fruits: ['kivi','banana','apple']

            }
        }
    }
</script>

<style lang="scss" scoped>

</style>