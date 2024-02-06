<script>
    import burger from "/burgerIcon.svg";
    import logo from "/logoIcon.svg";
    import close from "/closeIcon.svg";
    import search from "/searchIcon.svg";
    import SearchDialog from "./SearchDialog.svelte";

    const dialogAppearFn = () => {
        const dialog = document.querySelector("#searchDialog");
        dialog.showModal();
    };

    const toggleNavFn = () => {
        const nav = document.querySelector("nav");
        const attribute = nav.getAttribute('show')
        !Boolean(attribute) ? nav.setAttribute('show', true) : nav.removeAttribute('show')
    };
</script>

<style>
    img {
        cursor: pointer;
        width: 3rem;
    }

    header {
        position: sticky;
        top: 0;
        padding: 1rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
        background-color: black;
    }

    ul {
        border-radius: 1rem;
        background-color: var(--black-200);
        padding: 0 3rem;
        display: flex;
        align-items: center;
    }

    li {
        list-style: none;
        padding: 0.5rem 2rem;
        margin: 0.3rem;
        font-weight: var(--fw-600);
    }

    li:hover {
        border-radius: 10px;
        background-color: rgba(105, 102, 102, 0.518);
    }

    .burger,
    .close {
        display: none;
    }

    @media (width < 650px) {

        .burger,
        .close {
            display: block;
        }

        nav {
            padding: 1rem;
            background-color: black;
            position: absolute;
            inset: 0;
            min-height: 100dvh;
            transform: translateX(-1000px);
            transition: all 300ms ease-in;
        }

        ul {
            flex-direction: column;
            gap: 0;
            min-height: 40vh;
        }

        li {
            border: 10px double;
            margin: 2rem 0;
            width: 100%;
            padding: 1rem 2rem;
            font-size: 1.2rem;
            text-align: center;
            border-radius: 10px;
        }

        li:hover {
            background-color: white;
            color: black;
        }
    }
</style>

<header>
    <img on:click={toggleNavFn} class="burger" src={burger} alt="Menu" />
    <img src={logo} alt="Logo" />
    <nav id="navBar">
        <img on:click={toggleNavFn} class="close" src={close} alt="Close Menu" />
        <ul>
            <li>Movies</li>
            <li>Tv</li>
            <li>Favourites</li>
        </ul>
    </nav>
    <img on:click={dialogAppearFn} src={search} alt="Search" />
    <SearchDialog />
</header>