<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>VESTA — The Future of Trying On</title>

<style>

@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600&family=Playfair+Display:wght@400;500&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html {
    scroll-behavior: smooth;
}

body {
    background: #f5f2ec;
    color: #161616;
    font-family: "DM Sans", sans-serif;
}


/* ========================================
   NAVIGATION
======================================== */

nav {
    height: 76px;
    width: 100%;

    position: fixed;
    top: 0;
    left: 0;

    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 0 5%;

    background: rgba(245, 242, 236, 0.9);
    backdrop-filter: blur(18px);

    border-bottom: 1px solid rgba(0,0,0,0.06);

    z-index: 1000;
}

.logo {
    font-size: 23px;
    letter-spacing: 6px;
    font-weight: 500;
}

.nav-links {
    display: flex;
    gap: 32px;
    list-style: none;
}

.nav-links a {
    text-decoration: none;
    color: #171717;
    font-size: 13px;
}

.nav-right {
    display: flex;
    align-items: center;
    gap: 24px;
}

.search {
    font-size: 21px;
    cursor: pointer;
}

.waitlist {
    background: #171717;
    color: white;

    border: 0;
    border-radius: 30px;

    padding: 13px 23px;

    font-size: 12px;

    cursor: pointer;

    transition: transform .2s;
}

.waitlist:hover {
    transform: translateY(-2px);
}


/* ========================================
   HERO
======================================== */

.hero {
    min-height: 100vh;

    padding-top: 76px;

    display: grid;
    grid-template-columns: 45% 55%;
}


/* LEFT */

.hero-content {
    display: flex;
    flex-direction: column;
    justify-content: center;

    padding: 90px 8% 80px 12%;
}

.eyebrow {
    font-size: 10px;
    letter-spacing: 5px;
    color: #777;

    margin-bottom: 25px;
}

.hero-title {
    font-family: "Playfair Display", serif;

    font-size: clamp(58px, 6.3vw, 100px);

    line-height: .92;

    font-weight: 400;

    letter-spacing: -4px;

    margin-bottom: 32px;
}

.hero-description {
    max-width: 500px;

    color: #5f5f5f;

    font-size: 16px;

    line-height: 1.7;

    margin-bottom: 32px;
}

.hero-actions {
    display: flex;
    gap: 12px;

    margin-bottom: 60px;
}

.primary {
    background: #161616;
    color: white;

    border: none;

    padding: 17px 25px;

    border-radius: 30px;

    text-decoration: none;

    font-size: 13px;

    cursor: pointer;
}

.secondary {
    background: #e4dfd7;

    border: none;

    padding: 17px 24px;

    border-radius: 30px;

    font-size: 13px;

    cursor: pointer;
}


/* BENEFITS */

.benefits {
    display: flex;
    gap: 42px;
}

.benefit {
    display: flex;
    flex-direction: column;

    gap: 9px;

    max-width: 130px;
}

.benefit-icon {
    font-size: 25px;
}

.benefit-text {
    font-size: 12px;
    line-height: 1.4;
}


/* ========================================
   AI PERSON / HERO IMAGE
======================================== */

.hero-visual {
    position: relative;

    overflow: hidden;

    min-height: calc(100vh - 76px);

    background: #d7d0c5;
}


/*
IMPORTANT:

This is the ONLY place where the generated
website image is used.

Put the PNG in the same folder as index.html.
*/

.hero-photo {
    width: 100%;
    height: 100%;

    object-fit: cover;

    object-position: center;

    display: block;
}


/* ========================================
   MIRROR UI
======================================== */

.mirror-top {
    position: absolute;

    top: 45px;
    left: 45px;

    color: white;

    text-shadow: 0 2px 10px rgba(0,0,0,.4);
}

.mirror-logo {
    font-size: 20px;
    letter-spacing: 5px;
}

.mirror-time {
    font-size: 10px;
    margin-top: 5px;

    opacity: .85;
}


/* CLOTHING PANEL */

.clothing-panel {
    position: absolute;

    top: 90px;
    right: 40px;

    width: 130px;

    padding: 15px;

    background: rgba(35,35,32,.52);

    backdrop-filter: blur(15px);

    border: 1px solid rgba(255,255,255,.3);

    border-radius: 18px;

    color: white;
}

.panel-title {
    font-size: 10px;

    margin-bottom: 12px;

    opacity: .8;
}


/*
These are intentionally REAL clothing
placeholder cards rather than using the
entire hero image again.
*/

.garment {
    height: 58px;

    margin-bottom: 9px;

    border-radius: 10px;

    cursor: pointer;

    border: 1px solid rgba(255,255,255,.2);

    display: flex;

    align-items: center;
    justify-content: center;

    transition: .2s;
}

.garment:hover,
.garment.selected {
    border-color: white;
    transform: scale(1.03);
}

.garment-black {
    background: #171717;
}

.garment-white {
    background: #e9e5dd;
}

.garment-blazer {
    background:
        linear-gradient(
            135deg,
            #242424 0 48%,
            #111 49% 52%,
            #242424 53%
        );
}

.garment-burgundy {
    background: #73353c;
}

.garment-label {
    font-size: 9px;
    opacity: .8;
}


/* BOTTOM MIRROR CONTROLS */

.mirror-controls {
    position: absolute;

    bottom: 45px;
    right: 40px;

    display: flex;

    gap: 10px;
}

.mirror-button {
    border: none;

    background: rgba(255,255,255,.9);

    color: #171717;

    padding: 12px 18px;

    border-radius: 25px;

    font-size: 11px;

    cursor: pointer;
}


/* ========================================
   SECOND SECTION
======================================== */

.how {
    padding: 130px 7%;

    background: #eeebe4;
}

.how-grid {
    display: grid;

    grid-template-columns: 50% 50%;

    align-items: center;

    gap: 7%;
}


/* ========================================
   OUTFIT PREVIEW
======================================== */

.preview {
    position: relative;

    height: 540px;

    display: flex;

    align-items: center;

    justify-content: center;
}


/*
These are visual fashion cards.

They are NOT using the hero image.
They can later be replaced with actual
AI-generated outfit photos.
*/

.outfit-card {
    position: absolute;

    width: 225px;
    height: 350px;

    border-radius: 15px;

    overflow: hidden;

    box-shadow: 0 20px 45px rgba(0,0,0,.15);

    background: #d9d1c4;
}

.outfit-card.middle {
    z-index: 3;
}

.outfit-card.left {
    transform:
        translateX(-155px)
        rotate(-5deg);
}

.outfit-card.right {
    transform:
        translateX(155px)
        rotate(5deg);
}


/*
Abstract photo placeholders.
Replace their backgrounds with actual
outfit photos later.
*/

.outfit-image {
    height: 285px;

    width: 100%;
}

.casual-image {
    background:
        linear-gradient(
            180deg,
            #d6cec2 0%,
            #bdb09f 55%,
            #7f776e 56%,
            #777068 100%
        );
}

.business-image {
    background:
        linear-gradient(
            180deg,
            #cfc8bc 0%,
            #aaa49c 50%,
            #292929 51%,
            #111 100%
        );
}

.evening-image {
    background:
        linear-gradient(
            180deg,
            #d1c8c0 0%,
            #a89991 45%,
            #72383f 46%,
            #4d2028 100%
        );
}

.outfit-info {
    background: #faf8f3;

    height: 65px;

    padding: 13px;
}

.outfit-info strong {
    display: block;

    font-size: 12px;

    margin-bottom: 3px;
}

.outfit-info span {
    font-size: 9px;

    color: #888;
}


/* ========================================
   SECTION TEXT
======================================== */

.section-eyebrow {
    font-size: 10px;

    letter-spacing: 4px;

    color: #888;

    margin-bottom: 22px;
}

.section-title {
    font-family: "Playfair Display", serif;

    font-size: clamp(48px, 5vw, 75px);

    font-weight: 400;

    line-height: .96;

    letter-spacing: -3px;

    margin-bottom: 28px;
}

.section-description {
    color: #666;

    max-width: 470px;

    font-size: 14px;

    line-height: 1.7;

    margin-bottom: 42px;
}


/* ========================================
   STEPS
======================================== */

.steps {
    border-top: 1px solid #ccc;
}

.step {
    display: grid;

    grid-template-columns: 50px 1fr;

    gap: 20px;

    padding: 19px 0;

    border-bottom: 1px solid #ccc;
}

.step-number {
    width: 36px;
    height: 36px;

    border: 1px solid #aaa;

    border-radius: 50%;

    display: flex;

    align-items: center;
    justify-content: center;

    font-size: 10px;
}

.step h3 {
    font-size: 13px;

    margin-bottom: 4px;
}

.step p {
    font-size: 11px;

    color: #888;
}


/* ========================================
   TECHNOLOGY
======================================== */

.technology {
    padding: 130px 8%;

    background: #171717;

    color: white;
}

.tech-intro {
    max-width: 700px;

    margin-bottom: 75px;
}

.tech-intro .section-eyebrow {
    color: #888;
}

.tech-grid {
    display: grid;

    grid-template-columns: repeat(3, 1fr);

    gap: 20px;
}

.tech-card {
    min-height: 250px;

    padding: 32px;

    border: 1px solid #3b3b3b;

    border-radius: 20px;
}

.tech-number {
    font-size: 10px;

    color: #777;

    margin-bottom: 60px;
}

.tech-card h3 {
    font-family: "Playfair Display", serif;

    font-weight: 400;

    font-size: 27px;

    margin-bottom: 14px;
}

.tech-card p {
    color: #999;

    font-size: 12px;

    line-height: 1.6;
}


/* ========================================
   FINAL CTA
======================================== */

.final {
    padding: 150px 7%;

    background: #d8d0c1;

    text-align: center;
}

.final .section-title {
    max-width: 800px;

    margin: auto;
}

.final p {
    max-width: 430px;

    margin: 25px auto 35px;

    color: #666;

    font-size: 14px;

    line-height: 1.6;
}


/* ========================================
   FOOTER
======================================== */

footer {
    background: #171717;

    color: #777;

    padding: 35px 7%;

    display: flex;

    justify-content: space-between;

    font-size: 10px;
}


/* ========================================
   MOBILE
======================================== */

@media (max-width: 1000px) {

    .nav-links {
        display: none;
    }

    .hero {
        grid-template-columns: 1fr;
    }

    .hero-content {
        padding: 120px 8% 80px;
    }

    .hero-visual {
        min-height: 700px;
    }

    .how-grid {
        grid-template-columns: 1fr;
    }

    .tech-grid {
        grid-template-columns: 1fr;
    }
}


@media (max-width: 600px) {

    nav {
        height: 65px;
    }

    .waitlist {
        padding: 10px 15px;
    }

    .hero {
        padding-top: 65px;
    }

    .hero-content {
        padding: 90px 7% 65px;
    }

    .hero-title {
        font-size: 55px;
        letter-spacing: -3px;
    }

    .benefits {
        gap: 18px;
    }

    .hero-visual {
        min-height: 600px;
    }

    .clothing-panel {
        right: 15px;
        width: 105px;
    }

    .mirror-controls {
        right: 15px;
        bottom: 20px;
    }

    .preview {
        height: 400px;
    }

    .outfit-card {
        width: 165px;
        height: 270px;
    }

    .outfit-image {
        height: 215px;
    }

    .outfit-card.left {
        transform: translateX(-95px) rotate(-5deg);
    }

    .outfit-card.right {
        transform: translateX(95px) rotate(5deg);
    }

    footer {
        flex-direction: column;
        gap: 10px;
    }
}

</style>
</head>


<body>


<!-- ========================================
     NAVIGATION
======================================== -->

<nav>

    <div class="logo">
        VESTA
    </div>

    <ul class="nav-links">

        <li>
            <a href="#">Home</a>
        </li>

        <li>
            <a href="#technology">
                Technology
            </a>
        </li>

        <li>
            <a href="#benefits">
                Benefits
            </a>
        </li>

        <li>
            <a href="#how">
                How It Works
            </a>
        </li>

        <li>
            <a href="#about">
                About
            </a>
        </li>

    </ul>

    <div class="nav-right">

        <div class="search">
            ⌕
        </div>

        <button
            class="waitlist"
            onclick="joinWaitlist()"
        >
            Join the Waitlist
        </button>

    </div>

</nav>



<!-- ========================================
     HERO
======================================== -->

<section class="hero">


    <!-- LEFT -->

    <div class="hero-content">

        <div class="eyebrow">
            THE FUTURE OF TRYING ON
        </div>

        <h1 class="hero-title">
            See yourself<br>
            in any outfit
        </h1>

        <p class="hero-description">

            VESTA is an intelligent mirror that lets you try
            on clothes virtually — no changing rooms, no hassle.
            Explore styles, find your look, and shop with confidence.

        </p>


        <div class="hero-actions">

            <a
                href="#how"
                class="primary"
            >
                Try the virtual mirror →
            </a>

            <button
                class="secondary"
                onclick="watchVideo()"
            >
                Watch video&nbsp; ▷
            </button>

        </div>


        <div
            class="benefits"
            id="benefits"
        >

            <div class="benefit">

                <div class="benefit-icon">
                    ♧
                </div>

                <div class="benefit-text">
                    Endless styles
                </div>

            </div>


            <div class="benefit">

                <div class="benefit-icon">
                    ◇
                </div>

                <div class="benefit-text">
                    More sustainable shopping
                </div>

            </div>


            <div class="benefit">

                <div class="benefit-icon">
                    ♡
                </div>

                <div class="benefit-text">
                    Shop with confidence
                </div>

            </div>

        </div>

    </div>



    <!-- ========================================
         AI GENERATED PERSON IMAGE
    ======================================== -->

    <div class="hero-visual">

        <!--
        THIS IS THE GENERATED IMAGE.

        Keep this file next to index.html:

        wide_clean_modern_website_homepage_mockup_for_a.png
        -->

        <img
            class="hero-photo"
            src="wide_clean_modern_website_homepage_mockup_for_a.png"
            alt="AI generated model using VESTA"
        >


        <!-- Mirror information -->

        <div class="mirror-top">

            <div class="mirror-logo">
                VESTA
            </div>

            <div class="mirror-time">
                10:24 AM · Tue, 10 Sep
            </div>

        </div>


        <!-- Clothing selection -->

        <div class="clothing-panel">

            <div class="panel-title">
                Tops
            </div>


            <div
                class="garment garment-black selected"
                onclick="selectGarment(this, 'Black Top')"
            >
                <span class="garment-label">
                    BLACK
                </span>
            </div>


            <div
                class="garment garment-white"
                onclick="selectGarment(this, 'White Top')"
            >
                <span class="garment-label">
                    WHITE
                </span>
            </div>


            <div
                class="garment garment-blazer"
                onclick="selectGarment(this, 'Blazer')"
            >
                <span class="garment-label">
                    BLAZER
                </span>
            </div>


            <div
                class="garment garment-burgundy"
                onclick="selectGarment(this, 'Evening')"
            >
                <span class="garment-label">
                    EVENING
                </span>
            </div>

        </div>


        <!-- Bottom buttons -->

        <div class="mirror-controls">

            <button
                class="mirror-button"
                onclick="saveLook()"
            >
                ♡ Save Look
            </button>

            <button
                class="mirror-button"
                onclick="addToBag()"
            >
                ♧ Add to Bag
            </button>

        </div>

    </div>

</section>



<!-- ========================================
     HOW IT WORKS
======================================== -->

<section
    class="how"
    id="how"
>

    <div class="how-grid">


        <!-- OUTFIT CARDS -->

        <div class="preview">


            <div class="outfit-card left">

                <div class="outfit-image casual-image"></div>

                <div class="outfit-info">

                    <strong>
                        Casual
                    </strong>

                    <span>
                        Everyday comfort
                    </span>

                </div>

            </div>



            <div class="outfit-card middle">

                <div class="outfit-image business-image"></div>

                <div class="outfit-info">

                    <strong>
                        Business
                    </strong>

                    <span>
                        Professional and polished
                    </span>

                </div>

            </div>



            <div class="outfit-card right">

                <div class="outfit-image evening-image"></div>

                <div class="outfit-info">

                    <strong>
                        Evening
                    </strong>

                    <span>
                        Chic for special moments
                    </span>

                </div>

            </div>

        </div>



        <!-- TEXT -->

        <div>

            <div class="section-eyebrow">
                YOUR STYLE, IN SECONDS
            </div>

            <h2 class="section-title">
                Try.<br>
                Explore.<br>
                Decide.
            </h2>

            <p class="section-description">

                See how different outfits look on you instantly
                using advanced AI and computer vision.

                Discover new styles, mix and match, and find
                what suits you best — all in real time.

            </p>


            <div class="steps">


                <div class="step">

                    <div class="step-number">
                        01
                    </div>

                    <div>

                        <h3>
                            Stand in front of VESTA
                        </h3>

                        <p>
                            Our AI detects your body shape and creates a digital you.
                        </p>

                    </div>

                </div>


                <div class="step">

                    <div class="step-number">
                        02
                    </div>

                    <div>

                        <h3>
                            Browse and select
                        </h3>

                        <p>
                            Choose from a wide range of clothing and styles.
                        </p>

                    </div>

                </div>


                <div class="step">

                    <div class="step-number">
                        03
                    </div>

                    <div>

                        <h3>
                            See the magic
                        </h3>

                        <p>
                            Watch as the outfit appears on you virtually.
                        </p>

                    </div>

                </div>


                <div class="step">

                    <div class="step-number">
                        04
                    </div>

                    <div>

                        <h3>
                            Shop or save
                        </h3>

                        <p>
                            Like what you see? Save the look or shop instantly.
                        </p>

                    </div>

                </div>

            </div>


            <a
                href="#"
                class="primary"
                style="display:inline-block; margin-top:35px;"
                onclick="experience(); return false;"
            >
                Experience it now →
            </a>

        </div>

    </div>

</section>



<!-- ========================================
     TECHNOLOGY
======================================== -->

<section
    class="technology"
    id="technology"
>

    <div class="tech-intro">

        <div class="section-eyebrow">
            THE TECHNOLOGY
        </div>

        <h2 class="section-title">
            Your reflection,<br>
            reimagined.
        </h2>

    </div>


    <div class="tech-grid">


        <div class="tech-card">

            <div class="tech-number">
                01 / COMPUTER VISION
            </div>

            <h3>
                Understand
            </h3>

            <p>
                VESTA recognizes your body position,
                proportions and movement in real time.
            </p>

        </div>



        <div class="tech-card">

            <div class="tech-number">
                02 / AI FITTING
            </div>

            <h3>
                Transform
            </h3>

            <p>
                Clothing is digitally adapted to your body
                so you can visualize the complete look.
            </p>

        </div>



        <div class="tech-card">

            <div class="tech-number">
                03 / SMART SHOPPING
            </div>

            <h3>
                Decide
            </h3>

            <p>
                Compare outfits before buying and discover
                styles that genuinely work for you.
            </p>

        </div>

    </div>

</section>



<!-- ========================================
     FINAL CTA
======================================== -->

<section
    class="final"
    id="about"
>

    <div class="section-eyebrow">
        COMING SOON
    </div>

    <h2 class="section-title">
        Your wardrobe.<br>
        Reimagined.
    </h2>

    <p>
        The changing room is about to disappear.
        Be among the first to experience VESTA.
    </p>

    <button
        class="waitlist"
        onclick="joinWaitlist()"
    >
        Join the Waitlist
    </button>

</section>



<!-- ========================================
     FOOTER
======================================== -->

<footer>

    <span>
        © 2026 VESTA
    </span>

    <span>
        The future of virtual fitting
    </span>

</footer>



<script>

/* ========================================
   WAITLIST
======================================== */

function joinWaitlist() {

    const email = prompt(
        "Enter your email to join the VESTA waitlist:"
    );

    if (!email) return;

    if (!email.includes("@")) {

        alert("Please enter a valid email address.");

        return;
    }

    alert(
        "You're on the VESTA waitlist."
    );
}


/* ========================================
   GARMENT SELECTION
======================================== */

function selectGarment(element, name) {

    document
        .querySelectorAll(".garment")
        .forEach(item => {
            item.classList.remove("selected");
        });

    element.classList.add("selected");

    console.log(
        "Selected:",
        name
    );

}


/* ========================================
   SAVE
======================================== */

function saveLook() {

    alert(
        "Look saved to your VESTA wardrobe."
    );

}


/* ========================================
   SHOPPING
======================================== */

function addToBag() {

    alert(
        "The selected outfit has been added to your bag."
    );

}


/* ========================================
   VIDEO
======================================== */

function watchVideo() {

    alert(
        "The VESTA product video would open here."
    );

}


/* ========================================
   EXPERIENCE
======================================== */

function experience() {

    alert(
        "The virtual fitting experience would launch here."
    );

}

</script>

</body>
</html>
