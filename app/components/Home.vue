<template>
    <Page>
        <ActionBar>
            <Label class="h1" text="TO-DO List"></Label>
        </ActionBar>
        <ListView for="item in items" @itemTap="onItemTap" id="list">
            <v-template>
                <StackLayout orientation="horizontal">
                    <Label class="font-weight-bold h3" :text="item.content" textWrap="true"></Label>
                </StackLayout>
            </v-template>
        </ListView>
    </Page>
</template>

<script>
import Details from "./Details";

    export default {
        data: () => {
            return {
                items: [
                    {
                        content: "Call the president",
                        done: false
                    },
                    {
                        content: "Send a letter to my fiancee",
                        done: false
                    },
                    {
                        content: "Send missing emails",
                        done: false
                    },
                    {
                        content: "Buy a new car",
                        done: false
                    },
                    {
                        content: "Go to my cousin party",
                        done: false
                    },
                    {
                        content: "Go to the meeting with the big ones",
                        done: false
                    },
                    {
                        content: "Finish app for the mexican restaurant",
                        done: false
                    },
                    {
                        content: "Go to see the stores to put on a bar",
                        done: false
                    },
                    {
                        content: "Date with the best girl in the world",
                        done: false
                    },
                    {
                        content: "Go for some beers with the gang",
                        done: false
                    }, 
                    {
                        content: "Buy the tickets for the SuperBowl",
                        done: false
                    },
                    {
                        content: "Find a client for the airplane",
                        done: false
                    },
                    {
                        content: "Finish the 5th chapter of the book",
                        done: false
                    },
                    {
                        content: "Get a new PC",
                        done: false
                    },
                    {
                        content: "Take Zeus to the veterinary",
                        done: false
                    },
                    {
                        content: "Buy something to the Edu's baby",
                        done: false
                    },
                    {
                        content: "Cut my hair",
                        done: false
                    },
                    {
                        content: "Meeting with the software enterprise employees",
                        done: false
                    },
                    {
                        content: "Videocall with the enterprise president of England",
                        done: false
                    },
                    {
                        content: "Flight to New York",
                        done: false
                    }
                ]
            };
        },
        methods: {
            onItemTap(args) {
                const view = args.view;
                const page = view.page;
                const tappedItem = view.bindingContext;

                this.$navigateTo(Details, {
                    props: {
                        context: tappedItem,
                        animated: true,
                        transition: {
                            name: "slide",
                            duration: 100,
                            curve: "ease"
                    }}});
            }
        }
    }
</script>

<style scoped lang="css">    
@import '~@nativescript/theme/css/sky.css';

</style>
