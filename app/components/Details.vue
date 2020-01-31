<template>
    <Page>
        <ActionBar>
            <NavigationButton @tap="$navigateBack" android.systemIcon="ic_menu_back"/>
            <Label class="h1" text="Details"></Label>
        </ActionBar>
        <FlexboxLayout flexDirection="column" justifyContent="space-around">
            <Label textWrap="true" class="font-weight-bold h2 text-center" :text="item.content"></Label>
                <Button v-if="this.item.done" backgroundColor="green" textWrap="true" class="h2 text-center" text="DONE" @ontap="changeItemStat"></Button>
                <Button v-else textWrap="true" backgroundColor="red" class="h2 text-center" text="PENDING" @ontap="changeItemStat"></Button>
        </FlexboxLayout>
    </Page>
</template>

<script>
export default {
    props: ["context"],
    computed: {
        item() {
            return this.context || {};
        }
    },
    methods: {
        changeItemStat() {
           this.item.done = !this.item.done;
        }
    }
};
</script>

<style scoped>
@import '~@nativescript/theme/css/sky.css';

</style>