* {
    box-sizing: border-box;
}

body {
    margin: 0;
    font-family: "Segoe UI", SegoeUI, "Helvetica Neue", Helvetica, Arial, sans-serif;
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    color: #000;
    background-color: #fff;
}

a {
    text-decoration: none;
}



.container-normal {
    width: 90%;
    /* 有限制的時候要置中 */
    margin: 0 auto;
    max-width: 1600px;

    @media (max-width:860px) {
        width: 100%;
        padding: 0 20px;
    }
}

.container-full {
    width: 100%;
    margin: 0 auto;
    max-width: 1920px;

    display: flex;

    .w-100 {
        width: 100%;
    }
}

img {
    /* img 圖片對齊底部 */
    vertical-align: bottom;
}

/* =================================================== */
nav {
    /* background-color: plum; */
    width: 100%;
    height: 54px;
    display: flex;
    gap: 10px;
    justify-content: space-between;

    position: relative;

    a {
        &:focus {
            /* 放在boder外的輪廓 */
            outline: 3px dotted #0067b8;
            /* 縮放 */
            outline-offset: -4px;
        }

        .logo {
            /* background-color: aquamarine; */
            width: 137px;
            height: 54px;
            display: flex;
            align-items: center;
            justify-content: center;

            @media (max-width:860px) {
                position: absolute;
                left: 50%;
                transform: translateX(-50%);
            }

            img {
                width: 108px;
                height: 23px;
            }

        }
    }

    ul.pc-nav {
        /* background-color: plum; */
        list-style: none;
        width: 800px;
        /* height: 100%; */
        margin: 0;
        padding: 0;
        color: var(--uhf-header-link-color);
        list-style: none;

        display: flex;

        @media (max-width: 860px) {
            display: none;
        }

        li {
            height: 100%;
            display: flex;
            align-items: center;

            a {
                /* background-color: palevioletred; */
                width: auto;
                height: 100%;
                padding: 0 8px;
                /* border: 1px solid purple; */
                display: flex;
                align-items: center;
                cursor: pointer;
                color: #262626;
                font-size: 13px;
                text-decoration: none;

                &:focus {
                    /* 放在boder外的輪廓 */
                    outline: 3px dotted black;
                    /* 縮放 */
                    outline-offset: -4px;
                }
            }

            span {
                border-bottom: 2px solid transparent;
                color: #262626;

            }

            &:hover span {
                border-bottom: 2px solid black;
                color: #262626;
            }

        }
    }



    ul.func-nav {
        /* background-color: plum; */
        /* width: 80%; */
        color: var(--uhf-header-link-color);
        min-width: 250px;
        margin: 0;
        padding: 0;
        list-style: none;

        /* 讓他自動撐滿剩餘空間 */
        flex: 1;
        display: flex;
        justify-content: end;
        /* gap: 8px; */

        .hide-text {
            @media (max-width: 1500px) {
                display: none;
            }
        }

        .nav-search-icon {
            @media (max-width:860px) {
                position: absolute;
                left: 60px;
            }
        }

        .all-ms-label {
            width: auto;
            height: 100%;
            display: flex;
            align-items: center;
            padding: 0 8px;

            &:focus {
                background-color: #f2f2f2;
                outline: 3px dotted black;
                outline-offset: -4px;
            }

            @media (max-width:860px) {
                display: none;
            }
        }


        li {
            /* height: 100%; */
            /* display: flex; */
            align-items: center;
            justify-content: center;

            #all-ms {
                display: none;
                position: absolute;
                opacity: 0;
                width: 0;
                height: 0;

                &:checked~.dropdown-menu {
                    accent-color: rgb(255, 191, 191);
                    display: flex;
                }
            }

            span {
                font-size: 13px;
            }

            .dropdown-menu {
                background-color: #f2f2f2;
                width: 90%;
                /* height: 500px; */
                position: absolute;
                left: 50%;
                top: 100%;
                transform: translateX(-50%);


                display: none;
                flex-wrap: wrap;
                z-index: 999;

                @media (max-width:1200px) {
                    width: 100%;
                }

                @media (max-width:860px) {
                    display: none;
                }

                ul {
                    /* background-color: antiquewhite; */
                    display: flex;
                    flex-direction: column;
                    padding-left: 0;

                    list-style: none;
                    font-size: 13px;

                    width: calc(100%/6);

                    @media (max-width:1200px) {
                        width: calc(100%/5);
                    }

                    @media (max-width:1004px) {
                        width: calc(100%/4);
                    }

                    .title {
                        padding: 12px 12px 12px 24px;
                        color: #262626;
                        font-weight: bold;
                    }

                    li {

                        /* justify-content: flex-start; */
                        &:hover {
                            span {
                                border-bottom: 1px solid #616161;
                            }
                        }

                        a {
                            /* background-color: rgb(149, 213, 191); */
                            /* 要讓虛線填滿外框，要padding在a，讓li padding:0，
                            另外width:100%，display: inline-block，讓a自己撐滿整行，這樣虛線就會填滿整行 */
                            display: inline-block;
                            padding: 12px 24px;
                            width: 100%;

                            display: inline-block;
                            color: #616161;

                            &:hover {
                                background-color: lightgray;
                            }

                            &:focus {
                                color: #616161;
                                outline: 3px dotted #616161;
                                /* outline-offset: -1px; */
                            }

                            span {
                                border-bottom: 1px solid transparent;

                            }
                        }
                    }

                }

                ul.review-website-map {
                    background-color: #e6e6e6;
                    ;
                    width: 100%;
                    margin: auto;
                    flex-direction: column;
                    align-items: center;
                    border-bottom: 2px solid black;

                    li {
                        text-align: center;

                        &:focus {
                            background-color: #e6e6e6;
                            outline: 3px dotted black;
                        }

                        a {
                            text-align: center;
                            display: inline-block;
                        }
                    }

                }
            }

            a {
                /* background-color: palevioletred; */
                width: auto;
                height: 100%;
                padding: 1px 8px;

                display: flex;
                align-items: center;
                gap: 3px;
                cursor: pointer;
                color: #262626;
                font-size: 13px;

                &:focus {
                    outline: 3px dotted black;
                    outline-offset: -4px;
                }
            }



            span {
                border-bottom: 2px solid transparent;
                color: #262626;
            }

            &:hover span {
                border-bottom: 2px solid black;
                color: #262626;
            }


            .nav-chevron-down-icon {
                display: flex;
                align-items: center;
                justify-content: center;

                font-size: 8px;
            }

            .nav-search-icon {
                display: flex;
                align-items: center;
                justify-content: center;

                transform: scaleX(-1);
                font-size: 16px;
            }

            img {
                width: 40px;
                height: 36px;
            }
        }

    }
}


/* =========================================================== */
header {
    /* background-color: palevioletred; */
    width: 100%;
    /* height: 500px; */
    padding: 0 0 64px;
    /* margin-bottom: 100px; */
    position: relative;

    .card-all {
        /* background-color: cornflowerblue; */
        width: 550px;
        height: 280px;
        padding: 48px;

        position: absolute;
        top: 20%;
        left: 5%;

        @media (max-width:1084px) {
            background-color: #fff;
            width: 98%;
            height: auto;
            padding: 48px 52px 48px;
            /* 1. 覆蓋掉原本桌機版的 top 設定 */
            top: auto;
            /* 2. 讓卡片垂直基準線對齊圖片底部 */
            bottom: 0;
            /* 3. 讓卡片靠左 50% */
            left: 50%;
            /* 4. 關鍵：X軸往回推50%達成水平置中，Y軸往下推50%（也就是自身高度的一半）跨在底線上 */
            transform: translate(-50%, 50%);
            box-shadow: 0 .1875rem .4375rem 0 rgba(0, 0, 0, .13), 0 .0625rem .125rem 0 rgba(0, 0, 0, .11);
        }

        @media (max-width:860px) {
            width: 100%;
            bottom: -52px;
        }

        h1 {
            font-size: 37px;
            color: #000000;
            margin: 0 0 20px;

            @media (max-width:1400px) {
                font-size: 29px;
            }

            @media (max-width:1084px) {
                font-size: 24px;
                margin: 0 0 12px;
            }
        }

        .text {
            color: #000000;
            margin: 0 0 32px;

            @media (max-width:1084px) {
                margin: 0 0 24px;
            }
        }

        a.btn {
            width: 92px;
            height: 40px;
            background-color: #0067B8;
            border-radius: 2px;

            font-weight: 500;
            color: white;
            text-decoration: none;

            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 1px 1px 0 rgba(0, 0, 0, .13), 0 1px 2px 0 rgba(0, 0, 0, .11);

            &:hover {
                background-color: #004a7f;
            }

            &:focus {
                outline: 3px dotted #fff;
                outline-offset: -5px;
            }
        }

        .img-controls {
            background-color: palevioletred;
            width: 240px;
            height: 44px;
        }
    }
}

/* =========================================================== */
main {
    /* background-color: rgb(106, 23, 50); */
    width: 100%;
    position: relative;
    /* height: 2000px; */

    /* margin-bottom: 30px */


    section.three-choices {
        /* height: 104px; */
        /* background-color: lightblue; */
        margin: 0 0 50px;

        display: flex;
        justify-content: center;

        @media (max-width:1084px) {
            margin-top: 200px;
        }

        @media (max-width:584px) {
            flex-wrap: wrap;
            margin-bottom: 25px;
        }

        a {
            /* background-color: white; */
            /* width: calc(220px - 24px*2);
            height: calc(105px - 16px*2); */
            margin: 16px 24px;
            display: flex;
            flex-direction: column;
            align-items: center;
            /* justify-content: center; */

            &:hover {
                color: #0067b8;
            }

            &:focus span {
                outline: 3px dotted #0067b8;
            }

            img {
                width: 40px;
                height: 40px;
                margin: 0 0 8px;
            }

            span {
                width: 100%;
                font-size: 16px;
                font-weight: 500;
                line-height: 1.5;
                color: #0067b8;
                cursor: pointer;
                text-decoration: underline;

                text-align: center;
            }
        }
    }

    section.four-cards {
        /* height: 500px; */
        /* background-color: rgb(173, 230, 214); */
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        row-gap: 50px;

        .w-100 {
            width: 100%;
        }

        .one-card {
            background-color: #fff;
            width: calc((100% - 20px*3)/4);
            /* height: 480px; */
            box-shadow: 0 3px 7px 0 rgba(0, 0, 0, .13), 0 .0625rem .125rem 0 rgba(0, 0, 0, .11);
            display: flex;
            flex-direction: column;

            @media (max-width: 1084px) {
                width: calc((100% - 20px) / 2);
            }

            @media (max-width: 539px) {
                width: 100%;
            }

            .card-body {
                padding: 24px 24px 10px 24px;

                h2 {
                    margin: 0 0 16px;
                    font-size: 29px;

                    @media (max-width:1400px) {
                        font-size: 24px;
                    }
                }
            }

            .card-footer {
                padding: 16px 24px 32px;
                margin-top: auto;
                display: flex;
                flex-wrap: wrap;

                .btn {
                    background-color: #0067B8;
                    height: 40px;

                    border-radius: 2px;
                    color: #fff;
                    font-weight: 600;

                    text-align: left;

                    padding: 10px 12px;
                    margin: 8px 0;

                    &:hover {
                        background-color: #004a7f;
                    }

                    &:focus {
                        outline: 3px dotted #fff;
                        outline-offset: -5px;
                    }
                }

                .btn-2 {
                    /* background-color: #0067B8; */
                    height: 40px;

                    color: #0067B8;
                    font-weight: 600;
                    text-align: left;

                    padding: 10px 0;

                    &:hover {
                        background-color: #004a7f;
                    }

                    &:focus {
                        outline: 3px dotted #fff;
                        outline-offset: -5px;
                    }
                }
            }
        }
    }


    section.big-img {
        width: 100%;
        margin: 100px 0 0;
        max-width: 1920px;
        position: relative;

        .w-100 {
            width: 100%;
        }

        .card-all {
            background-color: #fff;
            width: 550px;
            height: 280px;
            padding: 48px;

            position: absolute;
            top: 50%;
            left: 5%;
            transform: translateY(-50%);

            @media (max-width:1084px) {
                width: 98%;
                height: auto;
                padding: 48px 52px 48px;
                /* 1. 覆蓋掉原本桌機版的 top 設定 */
                top: auto;
                /* 2. 讓卡片垂直基準線對齊圖片底部 */
                bottom: 0;
                /* 3. 讓卡片靠左 50% */
                left: 50%;
                /* 4. 關鍵：X軸往回推50%達成水平置中，Y軸往下推50%（也就是自身高度的一半）跨在底線上 */
                transform: translate(-50%, 50%);
                box-shadow: 0 .1875rem .4375rem 0 rgba(0, 0, 0, .13), 0 .0625rem .125rem 0 rgba(0, 0, 0, .11);
            }

            @media (max-width:860px) {
                width: 100%;
                bottom: -52px;
            }

            h2 {
                font-size: 37px;
                color: #000000;
                margin: 0 0 20px;

                @media (max-width:1400px) {
                    font-size: 29px;
                }

                @media (max-width:1084px) {
                    font-size: 24px;
                    margin: 0 0 12px;
                }
            }

            .text {
                color: #000000;
                margin: 0 0 32px;

                @media (max-width:1084px) {
                    margin: 0 0 24px;
                }
            }

            .btn {
                background-color: #0067B8;
                height: 40px;

                border-radius: 2px;
                color: #fff;
                font-weight: 600;
                text-align: left;

                padding: 10px 12px;
                margin: 8px 0;

                &:hover {
                    background-color: #004a7f;
                }
            }
        }

    }

    .business {

        padding-top: 50px;

        @media (max-width:1500px) {
            padding-top: 50px;
        }

        @media (max-width:1084px) {
            padding-top: 150px;
        }

        @media (max-width:860px) {
            padding-top: 200px;
        }

    }

    section.others {
        /* height: 200px; */
        margin-top: 60px;
        /* background-color: rgb(179, 134, 209); */
        display: flex;
        flex-direction: column;
        row-gap: 60px;
        padding: 20px 0;



        span {
            display: flex;
            align-items: center;
            gap: 20px;

            .fb-icon,
            .yt-icon {
                font-size: 25px;
                color: #000;
            }
        }
    }

    .sticky-area {
        /* background-color: plum; */
        width: 125px;
        height: calc(100% - 550px);

        position: absolute;
        right: 0;
        top: 550px;

        .sticky-go-top {
            background-color: #d3d3d3;
            width: 125px;
            height: 40px;

            position: sticky;
            left: 100%;
            top: calc(100% - 50px);
            transform: translateX(50%);

            padding: 10px 12px;
            color: #000;
            font-weight: 600;

            display: flex;
            align-items: center;
            justify-content: center;

            border-radius: 2px;
            cursor: pointer;

            @media (max-width:1500px) {
                left: auto;
                transform: none;
            }

            @media (max-width:1200px) {
                left: auto;
                transform: none;
            }

            @media (max-width:860px) {
                left: auto;
                transform: none;
            }

            &:hover {
                background-color: #fff;
                box-shadow: 0 .1875rem .4375rem 0 rgba(0, 0, 0, .13), 0 .0625rem .125rem 0 rgba(0, 0, 0, .11);
            }

            &:focus {
                background-color: #fff;
            }

            .go-top-arrow-up {
                width: 13px;
                margin-right: 10px;
            }
        }
    }
}

/* .go-top {
    background-color: #d3d3d3;
    width: 125px;
    height: 40px;

    position: absolute;
    left: 100%;
    bottom: 20px;

    padding: 10px 12px;
    color: #000;
    font-weight: 600;

    display: flex;
    align-items: center;
    justify-content: center;

    border-radius: 2px;
    cursor: pointer;

    &:hover {
        background-color: #fff;
        box-shadow: 0 .1875rem .4375rem 0 rgba(0, 0, 0, .13), 0 .0625rem .125rem 0 rgba(0, 0, 0, .11);
    }

    &:focus {
        background-color: #fff;
    }

    .go-top-arrow-up {
        width: 13px;
        margin-right: 10px;
    }
} */


/* ==================================== */
footer {
    background-color: #f2f2f2;
    width: 100%;
    /* height: 400px; */
    margin: 48px 0 0;
    color: #616161;

    @media (max-width:860px) {
        width: 100%;
    }

    .footer-menu {
        ul {
            /* background-color: antiquewhite; */
            display: flex;
            flex-direction: column;
            list-style: none;

            li {
                margin: 7px 0;

                &:hover {
                    span {
                        border-bottom: 1px solid #616161;
                    }
                }

                a {
                    /* background-color: rgb(149, 213, 191); */
                    /* padding: 8px 0; */
                    height: auto;

                    display: inline-block;
                    color: #616161;

                    /* &:focus { */
                    /* outline: unset; */

                    /* span { */
                    /* outline: 2px dashed red; */
                    /* outline-offset: -4px; */
                    /* } */
                    /* } */

                    &:focus {
                        color: #616161;
                        outline: 3px dotted #616161;
                        /* outline-offset: -1px; */
                    }

                    span {
                        border-bottom: 1px solid transparent;
                    }
                }
            }
        }
    }

    .footer-body {
        /* height: 100%; */
        background-color: #f2f2f2;
        padding-bottom: 3px;

        .footer-menu {
            display: flex;
            flex-wrap: wrap;

            ul {
                width: calc(100%/6);
                font-size: 11px;

                @media (max-width:1083px) {
                    width: calc(100%/3);
                }

                @media (max-width:540px) {
                    width: 100%;
                }
            }

            h2 {
                font-size: 15px;
                margin: 35px 0 4px 0;
            }

        }

        .footer-nav {
            display: flex;
            align-items: center;
            /* justify-content: center; */
            margin: 35px 0;

            @media (max-width:960px) {
                flex-direction: column;
                row-gap: 20px;
            }

            @media (max-width:760px) {
                margin-bottom: 0;
                padding: 30px 12px 16px;
            }

            ul.footer-nav-left {
                /* background-color: plum; */
                list-style: none;
                /* width: 800px; */
                /* height: 100%; */
                margin: 0;
                padding: 0;

                display: flex;

                @media (max-width:960px) {
                    width: 100%;
                    justify-content: start;
                }

                @media (max-width:760px) {
                    flex-direction: column;
                    row-gap: 10px;
                    justify-content: start;
                }

                li {
                    height: 100%;
                    /* display: flex;
                    align-items: center; */

                    a {
                        /* background-color: palevioletred; */
                        width: auto;
                        height: 100%;
                        padding: 0 12px;
                        /* border: 1px solid purple; */
                        display: flex;
                        align-items: center;

                        cursor: pointer;
                        color: #616161;
                        font-size: 11px;
                        text-decoration: none;


                        &:focus {
                            /* 放在boder外的輪廓 */
                            outline: 3px dotted #616161;
                            /* 縮放 */
                            outline-offset: -7px;
                        }

                        @media (max-width:760px) {
                            justify-content: start;
                        }
                    }

                    .footer-nav-left-icon {
                        display: flex;
                        align-items: center;
                        justify-content: center;

                        font-size: 20px;
                        margin-right: 5px;

                    }

                    span {
                        border-bottom: 1px solid transparent;
                        color: #616161;
                    }

                    &:hover span {
                        border-bottom: 1px solid #616161;
                        color: #616161;
                    }


                }
            }

            ul.footer-nav-right {
                /* background-color: plum; */
                /* width: 80%; */
                /* min-width: 220px; */
                margin: 0;
                padding: 0;
                list-style: none;

                /* 讓他自動撐滿剩餘空間 */
                flex: 1;
                display: flex;
                justify-content: end;
                gap: 8px;

                .hide-text {
                    @media (max-width: 1400px) {
                        display: none;
                    }
                }

                @media (max-width:960px) {
                    width: 100%;
                    justify-content: end;
                }


                @media (max-width:760px) {
                    justify-content: start;
                }

                li {
                    /* height: 100%; */
                    /* display: flex;
                    align-items: center;
                    justify-content: center; */

                    a {
                        /* background-color: palevioletred; */
                        width: auto;
                        height: 100%;
                        padding: 0 8px;

                        display: flex;
                        align-items: center;
                        gap: 3px;
                        cursor: pointer;
                        color: #262626;
                        font-size: 11px;

                        &:focus {
                            outline: 3px dotted black;
                            outline-offset: -4px;
                        }
                    }

                    span {
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        font-size: 11px;
                        border-bottom: 1px solid transparent;
                        color: #616161;
                    }

                    &:hover span {
                        font-size: 11px;
                        border-bottom: 1px solid #616161;
                        color: #616161;
                    }
                }
            }
        }
    }
}

/* ===============手機版menu=================== */
.ham-small {
    display: none;
    list-style: none;

    @media (max-width: 860px) {
        display: flex;
        align-items: center;
    }

    .ham-btn-label {
        /* background-color: thistle; */
        display: flex;
        align-items: center;
        justify-content: center;
        width: 28px;
        height: 100%;
        font-size: 25px;

        padding: 0 4px;

        .times-icon {
            display: none;
        }
    }

    #ham-btn {
        &:checked~.mobile-menu {
            accent-color: yellow;
            /* display: block; */
            display: flex;
        }

        &:checked~.ham-btn-label {
            .times-icon {
                display: block;
            }

            .lines-icon {
                display: none;
            }
        }
    }

    ul.mobile-menu {
        background-color: #f2f2f2;
        width: 100%;
        /* height: 500px; */
        margin: 0;
        padding: 0;
        /* display: flex; */
        flex-direction: column;
        display: none;
        list-style: none;
        z-index: 999;
        color: #262626;
        border-bottom: #000 solid 1px;

        font-size: 15px;
        text-decoration: none;

        position: absolute;
        left: 0;
        top: 100%;

        li {
            border-top: 1px solid #97959523;
            padding: 0;

            a {
                color: #262626;
                /* display: block;  */
                /* height: auto; */
                width: 100%;
                display: block;
                padding: 12px 8px 13px 15px;

                &:focus {
                    color: #262626;
                    outline: 2px dotted #262626;
                    border-bottom: 1px solid #262626;
                }

                &:hover {
                    span {
                        border-bottom: 2px solid #262626;
                    }
                }
            }

            .many-switch {
                &:checked~.sub-dropdown-menu {
                    /* accent-color: yellow; */
                    display: flex;
                }

                &:checked~.many-label {

                    .fa-chevron-up {
                        display: block;
                    }

                    .fa-chevron-down {
                        display: none;
                    }
                }
            }

            .many-label {
                /* display: inline-block; */
                display: flex;
                justify-content: space-between;
                width: 100%;
                /* display: inline-block; */
                padding: 12px 8px 13px 15px;

                &:focus {
                    outline: 2px dashed #262626;
                    /* outline-offset: -2px; */
                }

                .fa-chevron-up {
                    display: none;
                }
            }

            ul.sub-dropdown-menu {
                display: flex;
                flex-direction: column;
                list-style: none;
                padding: 0;

                display: none;
            }
        }
    }
}