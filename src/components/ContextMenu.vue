<template>
    <ul class='context-menu m-0' id="context-menu" >
        <li class="context-menu__item text-capitalize">
            <a class="context-menu__link" href="#">
                <span>Game</span>
                <span class="context-menu__icon">
                    <svg width="6" height="10" viewBox="0 0 3 6" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M-2.20586e-08 5.49536L-2.4021e-07 0.504643C-2.59825e-07 0.0558982 0.46513 -0.168475 0.736306 0.148163L2.87339 2.64352C3.0422 2.84063 3.0422 3.15937 2.87339 3.35438L0.736307 5.85184C0.46513 6.16847 -2.44337e-09 5.9441 -2.20586e-08 5.49536Z" fill="#676767"/>
                    </svg>
                </span>
            </a>
            <ul class="context-menu__submenu context-menu m-0">
                <li class="context-menu__item text-capitalize">
                    <a class="context-menu__link" href="#">
                        <span>Date</span>
                        <span class="context-menu__description">
                         Ctrl + Del
                        </span>
                    </a>
                </li>
                <li class="context-menu__item ">
                    <a class="context-menu__link" href="#">
                        <span>League</span>
                        <span class="context-menu__description">
                         Ctrl + Del
                        </span>
                    </a>
                </li>
            </ul>
        </li>

        <li class="context-menu__item text-capitalize">
            <a class="context-menu__link" href="#">
                <span>New</span>
                <span class="context-menu__icon">
                    <svg width="6" height="10" viewBox="0 0 3 6" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <path d="M-2.20586e-08 5.49536L-2.4021e-07 0.504643C-2.59825e-07 0.0558982 0.46513 -0.168475 0.736306 0.148163L2.87339 2.64352C3.0422 2.84063 3.0422 3.15937 2.87339 3.35438L0.736307 5.85184C0.46513 6.16847 -2.44337e-09 5.9441 -2.20586e-08 5.49536Z" fill="#676767"/>
                    </svg>
                </span>
            </a>
        </li>

        <li class="context-menu__item text-capitalize">
            <a class="context-menu__link" href="#">
                <span>New</span>
                <span class="context-menu__description">
                    Ctrl + A
                </span>
            </a>
        </li>

        <li class="context-menu__item text-capitalize">
            <a class="context-menu__link" href="#">
                <span>Delete</span>
                <span class="context-menu__description">
                    Ctrl + Del
                </span>
            </a>
        </li>
    </ul>
</template>

<script>

    export default {
        props: {
            contextMenu: {
                type: Boolean,
                default: false
            }
        }
    }
</script>

<style lang="scss">
    .context-menu {
        font-family: 'Poppins', sans-serif;
        list-style: none;
        width: 300px;
        box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.25);
        background: #F1F2F4;
        padding-left: 0;
        border-radius: 5px;
        top: -50000000000%;
        left: 0;
        position: absolute;

        &__item {
            font-size: 16px;
            text-transform: capitalize;
            position: relative;
            &:hover {
                .context-menu__submenu {
                    display: block;
                }
            }
        }
        &__link {
            color: #676767;
            text-decoration: none;
            display: block;
            padding-top: 0.7em;
            padding-bottom: 0.7em;
            padding-left: 1.5em;
            position: relative;
            &:hover {
                color: #657EFC;
                background: lighten(#676767, 50%);
                text-decoration: none;
            }
        }
        &__icon {
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translate(0, -50%);
        }
        &__description {
            position: absolute;
            right: 10px;
            top: 50%;
            transform: translate(0, -50%);
            color: lighten(#676767, 20%);
        }
        &__submenu {
            position: absolute;
            border-radius: 5px;
            top: 0px;
            left: 100%;
            display: none;
        }
    }
</style>