<template>
    <div class="gridWrapper">
        <div v-for="item in items" :key="item.id" class="gridWrapper__grid">
            <header class="gridWrapper__heading">
                <h2>{{item.animal}}</h2>
            </header>
            <section class="gridWrapper__content">
                <p class="gridWrapper__desc">{{item.description}}</p>
                <ul class="gridWrapper__list">
                    <li v-for="prosncons in item.prosncons" :key="prosncons">{{prosncons}}</li>
                </ul>
                <span class="gridWrapper__price">{{item.price}}</span>
            </section>
            <a href="#" class="gridWrapper__cta">Buy</a>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        items: {
            type: Object,
            required: true,
        }
    }

}
</script>

<style lang="scss" scoped>
    .gridWrapper {
        display: flex;
        flex-direction: column;

        @media(min-width: 1024px) {
            flex-direction: row;
        }

        &__grid {
            flex: 1;
            padding: 20px;
            margin: 20px;
            text-align: center;
            background-color: rgba(255, 255, 255, .3);

            @media(min-width: 1024px) {
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
            }
        }

        &__heading {
             margin-bottom: 20px;
             text-transform: uppercase;
             letter-spacing: 2px;
             color: #fff;
             font-size: 26px;

        }

        &__content {
            display: flex;
            flex-direction: column;
            align-items: center;

            @media(min-width: 1024px) {
                flex-direction: row;
                flex-wrap: wrap;
            }

            & > * {

                margin-bottom: 20px;
                @media(min-width: 1024px) {
                    flex: 1 1 100%;
                }
            }

        }

        &__cta {
            &,
            &:link,
            &:visited {
                display: inline-block;
                width: 150px;
                padding: 10px;
                border-radius: 4px;
                background-color: rgba(yellow,.8);
                text-decoration: none;
                color: #000;
                font-size: 18px;
                transition: all .3s;

                &:hover {
                    background-color: rgba(yellow,1);
                }

                @media(min-width: 1024px) {
                    align-self: flex-end;
                }
            }
        }

        &__list {
            list-style: none;

            @media(min-width: 768px) {
                width: 60%;
            }

            & > li {
                text-transform: capitalize;

                &:not(:last-child) {
                    padding: 10px 0;
                    border-bottom: 1px solid rgba(#444, .1);
                    margin-bottom: 20px;
                }
            }
        }

        &__price {
            display: block;
            font-size: 50px;
            font-weight: bold;
        }

        &__grid:nth-child(1) {
            // add styles for the first item
        }

        &__grid:nth-child(2) {
           .gridWrapper {

               &__price {
                    &::before {
                        content: "\0024";
                    }
                }
            }
        }

        &__grid:nth-child(3) {
            .gridWrapper {

               &__price {
                    &::before {
                        content: "\0024";
                    }
                }
            }
        }
    }

</style>
