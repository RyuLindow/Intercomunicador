<template> 
<div>
    <!--V-show boolean for the ShowHide toggle method-->
    <div v-show="showtickets">
        <div class="column-headers">
            <div class="column-header blue">
                <p class="column-header__text">
                    Creation date
                </p>
            </div>
            <div class="column-header light-blue">
                <p class="column-header__text">
                    Avg. first response
                </p>
            </div>
            <div class="column-header blue">
                <p class="column-header__text">
                    Avg. handling time
                </p>
            </div>
            <div class="column-header column-header--small light-blue">
                <p class="column-header__text">
                    Within
                </p>
            </div>
            <div class="column-header column-header--small light-blue">
                <p class="column-header__text">
                    Outside
                </p>
            </div>
            <div class="column-header blue">
                <p class="column-header__text">
                    Tickets
                </p>
            </div>
        </div>
        <AllTicketsStats />
    </div>
</div>
    
</template>

<script>
import AllTicketsStats from "@/components/allTicketsStats.vue";

export default {
    components: {
        AllTicketsStats,
    },

    //Part of the ShowHide button toggle method emit
    props: {
        showtickets: {
            type: Boolean,
        }
    },
}
</script>

<style scoped lang="scss">
/*all-tickets__column-headers*/
.column-headers{
    display: flex;
    flex-direction: row;
}

.column-header {
    display: flex; 
    flex: 2;
    font-weight: 700;
    font-size: 2rem;
    height: 5rem;
    margin-right: 0.8rem;
    margin-top: 1rem;
    box-shadow: 3px 3px 6px 0px rgba(0,0,0,0.5);
}

.column-header:last-of-type { /*no margin on the last element*/
    margin-right: 0;
}

.column-header--small {
    flex: 1;
}

.column-header__text {
    margin: auto 1.25rem; /* centers the text in the div + the display: flex on the parent */ 
}
</style>