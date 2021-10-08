<template>

</template>

<script lang="ts">
import {
    Component,
    Prop,
    Vue
} from 'vue-property-decorator';
@Component({
    components: {},
})
export default class Header extends Vue {
    @Prop() todos!: Array<Todo>
}
</script>

<style lang="">

</style>
