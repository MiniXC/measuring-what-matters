<script>
    import { onMount } from "svelte";

    onMount(() => {
        // Get all "navbar-burger" elements
        const $navbarBurgers = Array.prototype.slice.call(
            document.querySelectorAll(".navbar-burger"),
            0,
        );

        // Add a click event on each of them
        $navbarBurgers.forEach((el) => {
            el.addEventListener("click", () => {
                // Get the target from the "data-target" attribute
                let target = document.getElementById(el.dataset.target);
                // Toggle the "is-active" class on both the "navbar-burger" and the "navbar-menu"
                el.classList.toggle("is-active");
                target.classList.toggle("is-active");
            });
        });

        // Smooth scrolling for anchor links
        const navbarItems = document.querySelectorAll(".navbar-item");
        navbarItems.forEach((item) => {
            item.addEventListener("click", (e) => {
                const href = item.getAttribute("href");
                if (href && href.startsWith("#")) {
                    e.preventDefault();
                    const targetId = href.substring(1);
                    const targetElement = document.getElementById(targetId);
                    if (targetElement) {
                        targetElement.scrollIntoView({
                            behavior: "smooth",
                            block: "start",
                        });
                    }
                }
            });
        });
    });
</script>

<nav class="navbar" aria-label="main navigation">
    <div class="navbar-brand">
        <a class="navbar-item" href="#home">
            <strong>Measuring What Matters</strong>
        </a>

        <button
            class="navbar-burger"
            aria-label="menu"
            aria-expanded="false"
            data-target="navbarBasicExample"
        >
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
            <span aria-hidden="true"></span>
        </button>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
        <div class="navbar-end">
            <a class="navbar-item" href="#home">Home</a>
            <a class="navbar-item" href="#cards">Pitfalls</a>
            <a class="navbar-item" href="#qa">Q&A</a>
            <a class="navbar-item" href="#huggingface">Demo</a>
        </div>
    </div>
</nav>
