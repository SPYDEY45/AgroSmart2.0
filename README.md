# AgroSmart2.0
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>AgroSmart | Smart Agriculture Assistant</title>

  <!-- Bootstrap 5 -->
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css"
    rel="stylesheet"
  >

  <!-- Bootstrap Icons -->
  <link
    href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css"
    rel="stylesheet"
  >

  <style>

    /* =========================================
       GLOBAL
    ========================================= */

    :root {
      --green: #198754;
      --dark: #0b3d2e;
      --deep: #062b20;
      --lime: #a8df65;
      --cream: #f7fbf4;
      --brown: #9b6b43;
      --text: #19352b;
      --muted: #6c8178;
    }

    * {
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", sans-serif;
      color: var(--text);
      background: var(--cream);
      overflow-x: hidden;

      animation: pageIn 0.8s ease both;
    }


    /* =========================================
       ANIMATIONS
    ========================================= */

    @keyframes pageIn {
      from {
        opacity: 0;
      }

      to {
        opacity: 1;
      }
    }

    @keyframes navDown {
      from {
        opacity: 0;
        transform: translateY(-25px);
      }

      to {
        opacity: 1;
        transform: none;
      }
    }

    @keyframes heroLeft {
      from {
        opacity: 0;
        transform: translateX(-55px);
      }

      to {
        opacity: 1;
        transform: none;
      }
    }

    @keyframes heroRight {
      from {
        opacity: 0;
        transform: translateX(55px) scale(0.94);
      }

      to {
        opacity: 1;
        transform: none;
      }
    }

    @keyframes float {
      0%, 100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(-12px);
      }
    }

    @keyframes pulse {
      0%, 100% {
        box-shadow: 0 0 0 0 rgba(25,135,84,0.25);
      }

      50% {
        box-shadow: 0 0 0 15px rgba(25,135,84,0);
      }
    }

    @keyframes rise {
      from {
        opacity: 0;
        transform: translateY(35px);
      }

      to {
        opacity: 1;
        transform: none;
      }
    }


    /* =========================================
       NAVBAR
    ========================================= */

    .navbar {
      background: rgba(255,255,255,0.92) !important;
      backdrop-filter: blur(14px);

      box-shadow:
        0 8px 30px rgba(11,61,46,0.08);

      animation: navDown 0.8s ease both;
    }

    .brand {
      font-size: 1.45rem;
      font-weight: 800;
      color: var(--dark) !important;
      letter-spacing: -0.5px;
    }

    .brand i {
      color: var(--green);
    }

    .nav-link {
      position: relative;
      font-weight: 600;
      color: #39554a !important;
      margin: 0 5px;
    }

    .nav-link::after {
      content: "";

      position: absolute;

      left: 12px;
      right: 12px;
      bottom: 2px;

      height: 2px;

      background: var(--green);

      transform: scaleX(0);
      transform-origin: center;

      transition: 0.3s;
    }

    .nav-link:hover::after,
    .nav-link.active::after {
      transform: scaleX(1);
    }

    .btn-nav {
      border-radius: 999px;
      padding: 0.55rem 1.1rem;
      font-weight: 700;
    }


    /* =========================================
       HERO
    ========================================= */

    .hero {
      min-height: 680px;

      position: relative;

      overflow: hidden;

      display: flex;

      align-items: center;

      background:
        radial-gradient(
          circle at 75% 25%,
          rgba(168,223,101,0.28),
          transparent 28%
        ),
        linear-gradient(
          135deg,
          #eff9e9 0%,
          #f8fcf6 48%,
          #e7f5e9 100%
        );
    }

    .hero::before,
    .hero::after {
      content: "";

      position: absolute;

      border-radius: 50%;

      filter: blur(2px);

      opacity: 0.35;
    }

    .hero::before {
      width: 330px;
      height: 330px;

      background: var(--lime);

      right: -130px;
      top: -130px;
    }

    .hero::after {
      width: 230px;
      height: 230px;

      background: #8fd3b0;

      left: -100px;
      bottom: -90px;
    }

    .hero-content {
      position: relative;

      z-index: 2;

      animation:
        heroLeft 1s 0.15s ease both;
    }

    .eyebrow {
      display: inline-flex;

      align-items: center;

      gap: 8px;

      padding: 8px 14px;

      border-radius: 999px;

      background: #e0f3df;

      color: var(--dark);

      font-size: 0.88rem;

      font-weight: 800;

      margin-bottom: 18px;
    }

    .eyebrow i {
      color: var(--green);
    }

    .hero h1 {
      font-size: clamp(2.8rem, 6vw, 5.5rem);

      line-height: 1;

      font-weight: 900;

      letter-spacing: -3px;

      color: var(--deep);

      margin-bottom: 22px;
    }

    .hero h1 span {
      color: var(--green);
    }

    .hero p {
      font-size: 1.12rem;

      line-height: 1.8;

      color: var(--muted);

      max-width: 620px;
    }

    .hero-buttons {
      display: flex;

      gap: 12px;

      flex-wrap: wrap;

      margin-top: 28px;
    }

    .btn-main,
    .btn-outline-main {
      border-radius: 14px;

      padding: 13px 20px;

      font-weight: 800;

      transition: 0.3s;
    }

    .btn-main {
      color: #fff;

      background: var(--green);

      border: 2px solid var(--green);

      box-shadow:
        0 12px 25px rgba(25,135,84,0.2);
    }

    .btn-main:hover {
      transform: translateY(-4px);

      box-shadow:
        0 18px 32px rgba(25,135,84,0.28);

      background: #157347;

      color: #fff;
    }

    .btn-outline-main {
      color: var(--dark);

      background: #fff;

      border: 2px solid #d4e7d9;
    }

    .btn-outline-main:hover {
      transform: translateY(-4px);

      border-color: var(--green);

      color: var(--green);
    }


    /* =========================================
       HERO VISUAL
    ========================================= */

    .hero-visual {
      position: relative;

      min-height: 480px;

      animation:
        heroRight 1s 0.25s ease both;
    }

    .farm-card {
      position: absolute;

      inset: 30px 20px 30px 40px;

      background: rgba(255,255,255,0.88);

      border: 1px solid rgba(25,135,84,0.12);

      border-radius: 32px;

      box-shadow:
        0 30px 70px rgba(11,61,46,0.16);

      overflow: hidden;
    }

    .farm-sky {
      height: 52%;

      background:
        linear-gradient(
          180deg,
          #bce8f0,
          #e8f7e6
        );

      position: relative;
    }

    .sun {
      position: absolute;

      width: 80px;
      height: 80px;

      border-radius: 50%;

      background: #ffd66b;

      top: 42px;
      right: 48px;

      box-shadow:
        0 0 50px rgba(255,214,107,0.65);
    }

    .cloud {
      position: absolute;

      width: 90px;
      height: 30px;

      border-radius: 30px;

      background: #fff;

      opacity: 0.85;
    }

    .cloud::before,
    .cloud::after {
      content: "";

      position: absolute;

      border-radius: 50%;

      background: #fff;
    }

    .cloud::before {
      width: 42px;
      height: 42px;

      left: 14px;
      top: -22px;
    }

    .cloud::after {
      width: 32px;
      height: 32px;

      left: 45px;
      top: -14px;
    }

    .c1 {
      left: 45px;
      top: 55px;
    }

    .c2 {
      left: 170px;
      top: 120px;

      transform: scale(0.7);
    }

    .field {
      position: absolute;

      bottom: 0;

      left: 0;
      right: 0;

      height: 56%;

      background:
        linear-gradient(
          170deg,
          transparent 0 15%,
          rgba(43,118,60,0.25) 16% 17%,
          transparent 18% 30%,
          rgba(43,118,60,0.2) 31% 32%,
          transparent 33%
        ),
        linear-gradient(
          180deg,
          #77bd55,
          #2f7d3d
        );

      clip-path:
        polygon(
          0 20%,
          100% 0,
          100% 100%,
          0 100%
        );
    }

    .crop-row {
      position: absolute;

      left: 8%;
      right: 8%;
      bottom: 12%;

      display: flex;

      justify-content: space-around;

      font-size: 2.1rem;

      color: #e4f4bd;
    }


    /* =========================================
       FLOATING CARDS
    ========================================= */

    .floating-card {
      position: absolute;

      background: #fff;

      border-radius: 18px;

      padding: 14px 17px;

      box-shadow:
        0 18px 35px rgba(11,61,46,0.15);

      display: flex;

      align-items: center;

      gap: 12px;

      font-weight: 800;

      z-index: 3;
    }

    .floating-card i {
      width: 42px;
      height: 42px;

      border-radius: 13px;

      display: grid;

      place-items: center;

      background: #e4f5e6;

      color: var(--green);

      font-size: 1.2rem;
    }

    .fc1 {
      top: 8%;
      left: 0;

      animation:
        float 4s ease-in-out infinite;
    }

    .fc2 {
      right: 0;
      bottom: 14%;

      animation:
        float 4.5s 0.5s ease-in-out infinite;
    }

    .fc3 {
      left: 10%;
      bottom: 0;

      animation:
        float 5s 1s ease-in-out infinite;
    }


    /* =========================================
       SECTIONS
    ========================================= */

    .section {
      padding: 95px 0;
    }

    .section-label {
      color: var(--green);

      font-weight: 800;

      text-transform: uppercase;

      letter-spacing: 2px;

      font-size: 0.78rem;
    }

    .section-title {
      font-weight: 900;

      color: var(--deep);

      font-size: clamp(2rem,4vw,3.2rem);

      letter-spacing: -1.5px;
    }

    .section-subtitle {
      color: var(--muted);

      max-width: 680px;

      margin: auto;

      line-height: 1.8;
    }


    /* =========================================
       FEATURE CARDS
    ========================================= */

    .feature-card {
      height: 100%;

      padding: 28px;

      border: 1px solid #e2eee4;

      border-radius: 24px;

      background: #fff;

      box-shadow:
        0 12px 30px rgba(11,61,46,0.05);

      transition: 0.35s ease;

      opacity: 0;

      animation:
        rise 0.7s ease forwards;
    }

    .feature-card:nth-child(1) {
      animation-delay: 0.05s;
    }

    .feature-card:nth-child(2) {
      animation-delay: 0.12s;
    }

    .feature-card:nth-child(3) {
      animation-delay: 0.19s;
    }

    .feature-card:nth-child(4) {
      animation-delay: 0.26s;
    }

    .feature-card:nth-child(5) {
      animation-delay: 0.33s;
    }

    .feature-card:nth-child(6) {
      animation-delay: 0.40s;
    }

    .feature-card:nth-child(7) {
      animation-delay: 0.47s;
    }

    .feature-card:nth-child(8) {
      animation-delay: 0.54s;
    }

    .feature-card:hover {
      transform: translateY(-10px);

      box-shadow:
        0 25px 50px rgba(11,61,46,0.12);

      border-color: #cde5d2;
    }

    .feature-icon {
      width: 60px;
      height: 60px;

      border-radius: 18px;

      display: grid;

      place-items: center;

      background: #e8f6e9;

      color: var(--green);

      font-size: 1.65rem;

      margin-bottom: 22px;

      transition: 0.35s;
    }

    .feature-card:hover .feature-icon {
      transform:
        scale(1.12)
        rotate(-5deg);

      background: var(--green);

      color: #fff;
    }

    .feature-card h5 {
      font-weight: 850;

      color: var(--dark);
    }

    .feature-card p {
      color: var(--muted);

      line-height: 1.7;

      margin-bottom: 0;
    }


    /* =========================================
       DASHBOARD PREVIEW
    ========================================= */

    .preview-section {
      background: #eef7ef;
    }

    .dashboard-window {
      background: #fff;

      border-radius: 28px;

      overflow: hidden;

      box-shadow:
        0 30px 80px rgba(11,61,46,0.12);

      border: 1px solid #dceade;

      animation:
        pulse 4s 1s infinite;
    }

    .window-bar {
      padding: 14px 18px;

      background: #f8fbf8;

      border-bottom: 1px solid #e6eee7;

      display: flex;

      align-items: center;

      gap: 7px;
    }

    .dot {
      width: 10px;
      height: 10px;

      border-radius: 50%;

      background: #b8c9be;
    }

    .dash-body {
      padding: 24px;
    }

    .mini-stat {
      border: 1px solid #e4eee6;

      border-radius: 18px;

      padding: 18px;

      background: #fff;
    }

    .mini-stat i {
      font-size: 1.3rem;

      color: var(--green);
    }

    .mini-stat strong {
      display: block;

      font-size: 1.55rem;

      color: var(--dark);
    }

    .mini-stat small {
      color: var(--muted);
    }

    .chart {
      height: 190px;

      border-radius: 18px;

      background:
        linear-gradient(
          180deg,
          rgba(25,135,84,0.08),
          rgba(25,135,84,0.01)
        ),
        repeating-linear-gradient(
          to bottom,
          #fff 0,
          #fff 37px,
          #edf4ee 38px
        );

      position: relative;

      overflow: hidden;
    }

    .chart svg {
      width: 100%;
      height: 100%;
    }


    /* =========================================
       HOW IT WORKS
    ========================================= */

    .step {
      text-align: center;

      position: relative;
    }

    .step-number {
      width: 72px;
      height: 72px;

      border-radius: 22px;

      display: grid;

      place-items: center;

      margin: 0 auto 20px;

      background: var(--dark);

      color: #fff;

      font-weight: 900;

      font-size: 1.4rem;

      transition: 0.5s;
    }

    .step:hover .step-number {
      transform:
        scale(1.12)
        rotate(360deg);

      background: var(--green);
    }

    .step h5 {
      font-weight: 850;

      color: var(--dark);
    }

    .step p {
      color: var(--muted);

      line-height: 1.7;
    }


    /* =========================================
       CTA
    ========================================= */

    .cta {
      margin: 0 0 90px;

      border-radius: 34px;

      padding: 65px 30px;

      color: #fff;

      text-align: center;

      background:
        radial-gradient(
          circle at 20% 20%,
          rgba(168,223,101,0.25),
          transparent 25%
        ),
        radial-gradient(
          circle at 85% 80%,
          rgba(255,255,255,0.12),
          transparent 25%
        ),
        linear-gradient(
          135deg,
          #0b3d2e,
          #198754
        );

      overflow: hidden;

      position: relative;
    }

    .cta h2 {
      font-weight: 900;

      animation:
        rise 0.8s ease both;
    }

    .cta p {
      opacity: 0.84;

      max-width: 620px;

      margin: 14px auto 25px;

      line-height: 1.8;
    }

    .cta .btn {
      background: #fff;

      color: var(--dark);

      border: 0;

      border-radius: 14px;

      padding: 13px 22px;

      font-weight: 800;

      transition: 0.3s;
    }

    .cta .btn:hover {
      transform:
        translateY(-4px)
        scale(1.02);
    }


    /* =========================================
       FOOTER
    ========================================= */

    footer {
      background: #062b20;

      color: #cfe3d8;

      padding: 55px 0 25px;
    }

    footer .brand {
      color: #fff !important;
    }

    footer h6 {
      color: #fff;

      font-weight: 800;
    }

    footer a {
      color: #a9c6b7;

      text-decoration: none;

      display: block;

      margin: 8px 0;

      transition: 0.25s;
    }

    footer a:hover {
      color: #fff;

      transform: translateX(4px);
    }

    .copyright {
      border-top:
        1px solid rgba(255,255,255,0.1);

      margin-top: 35px;

      padding-top: 20px;

      font-size: 0.9rem;

      color: #91afa0;
    }


    /* =========================================
       RESPONSIVE
    ========================================= */

    @media (max-width: 991px) {

      .hero {
        min-height: auto;

        padding:
          100px 0
          70px;
      }

      .hero-visual {
        min-height: 430px;

        margin-top: 35px;
      }

      .farm-card {
        inset:
          25px
          10px
          25px
          20px;
      }

      .fc1 {
        left: 0;
      }

      .fc2 {
        right: 0;
      }
    }


    @media (max-width: 575px) {

      .section {
        padding: 70px 0;
      }

      .hero h1 {
        letter-spacing: -2px;
      }

      .hero-buttons .btn {
        width: 100%;
      }

      .hero-visual {
        min-height: 360px;
      }

      .farm-card {
        inset:
          20px
          0;
      }

      .floating-card {
        font-size: 0.78rem;

        padding:
          9px
          11px;
      }

      .floating-card i {
        width: 34px;
        height: 34px;
      }

      .fc3 {
        left: 0;
      }

      .fc2 {
        right: 0;
      }
    }

  </style>
</head>


<body>


<!-- =========================================
     NAVBAR
========================================= -->

<nav class="navbar navbar-expand-lg sticky-top">

  <div class="container py-2">

    <a
      class="navbar-brand brand"
      href="#home"
    >
      <i class="bi bi-leaf-fill me-2"></i>
      AgroSmart
    </a>


    <button
      class="navbar-toggler border-0 shadow-none"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#mainNav"
    >
      <i class="bi bi-list fs-2"></i>
    </button>


    <div
      class="collapse navbar-collapse"
      id="mainNav"
    >

      <ul
        class="navbar-nav ms-auto align-items-lg-center"
      >

        <li class="nav-item">
          <a
            class="nav-link active"
            href="#home"
          >
            Home
          </a>
        </li>

        <li class="nav-item">
          <a
            class="nav-link"
            href="#features"
          >
            Features
          </a>
        </li>

        <li class="nav-item">
          <a
            class="nav-link"
            href="#how"
          >
            How It Works
          </a>
        </li>

        <li class="nav-item">
          <a
            class="nav-link"
            href="#market"
          >
            Marketplace
          </a>
        </li>

        <li class="nav-item ms-lg-2">

          <a
            class="btn btn-main btn-nav"
            href="#start"
          >
            Get Started
          </a>

        </li>

      </ul>

    </div>

  </div>

</nav>



<!-- =========================================
     HERO
========================================= -->

<header
  class="hero"
  id="home"
>

  <div class="container position-relative">

    <div class="row align-items-center g-5">


      <!-- HERO TEXT -->

      <div class="col-lg-6 hero-content">

        <div class="eyebrow">

          <i class="bi bi-stars"></i>

          Smart Agriculture • One Platform

        </div>


        <h1>

          Grow smarter.

          <br>

          <span>Farm better.</span>

        </h1>


        <p>

          AgroSmart brings crop guidance, weather information,
          market prices, expert support and a farmer marketplace
          together in one simple, farmer-friendly platform.

        </p>


        <div class="hero-buttons">

          <a
            href="#features"
            class="btn btn-main"
          >

            Explore Features

            <i class="bi bi-arrow-right ms-1"></i>

          </a>


          <a
            href="#market"
            class="btn btn-outline-main"
          >

            <i class="bi bi-shop me-1"></i>

            Farmer Marketplace

          </a>

        </div>


        <div
          class="d-flex gap-4 mt-4 flex-wrap"
        >

          <small class="text-secondary">

            <i
              class="bi bi-check-circle-fill text-success me-1"
            ></i>

            Crop Guidance

          </small>


          <small class="text-secondary">

            <i
              class="bi bi-check-circle-fill text-success me-1"
            ></i>

            Market Access

          </small>


          <small class="text-secondary">

            <i
              class="bi bi-check-circle-fill text-success me-1"
            ></i>

            Expert Support

          </small>

        </div>

      </div>



      <!-- HERO VISUAL -->

      <div class="col-lg-6">

        <div class="hero-visual">


          <div class="farm-card">

            <div class="farm-sky">

              <div class="sun"></div>

              <div class="cloud c1"></div>

              <div class="cloud c2"></div>

              <div class="field"></div>


              <div class="crop-row">

                <i class="bi bi-flower1"></i>

                <i class="bi bi-tree-fill"></i>

                <i class="bi bi-flower1"></i>

                <i class="bi bi-tree-fill"></i>

                <i class="bi bi-flower1"></i>

              </div>

            </div>

          </div>



          <!-- WEATHER CARD -->

          <div class="floating-card fc1">

            <i class="bi bi-cloud-sun"></i>

            <div>

              <small class="text-secondary d-block">
                Weather
              </small>

              Farming Forecast

            </div>

          </div>



          <!-- MARKET CARD -->

          <div class="floating-card fc2">

            <i class="bi bi-graph-up-arrow"></i>

            <div>

              <small class="text-secondary d-block">
                Market
              </small>

              Price Insights

            </div>

          </div>



          <!-- RECOMMENDATION CARD -->

          <div class="floating-card fc3">

            <i class="bi bi-stars"></i>

            <div>

              <small class="text-secondary d-block">
                Smart
              </small>

              Crop Recommendation

            </div>

          </div>


        </div>

      </div>

    </div>

  </div>

</header>



<!-- =========================================
     FEATURES
========================================= -->

<section
  class="section"
  id="features"
>

  <div class="container">


    <div class="text-center mb-5">

      <div class="section-label mb-2">

        Everything in one place

      </div>


      <h2 class="section-title">

        Tools built around the farmer

      </h2>


      <p class="section-subtitle">

        From choosing a crop to finding a buyer,
        AgroSmart connects useful agricultural services
        through a single digital platform.

      </p>

    </div>



    <div class="row g-4">


      <!-- CARD 1 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-flower1"></i>

          </div>

          <h5>
            Crop Information
          </h5>

          <p>

            Explore crop seasons, soil requirements,
            water needs, cultivation information and precautions.

          </p>

        </div>

      </div>



      <!-- CARD 2 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-stars"></i>

          </div>

          <h5>
            Smart Recommendation
          </h5>

          <p>

            Get educational crop suggestions based on
            soil, season, water availability and location.

          </p>

        </div>

      </div>



      <!-- CARD 3 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-cloud-sun"></i>

          </div>

          <h5>
            Weather
          </h5>

          <p>

            Keep weather information accessible for
            better planning and informed farming decisions.

          </p>

        </div>

      </div>



      <!-- CARD 4 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-bug"></i>

          </div>

          <h5>
            Crop Diseases
          </h5>

          <p>

            Learn about common crop problems, symptoms,
            causes and general management guidance.

          </p>

        </div>

      </div>



      <!-- CARD 5 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-shop-window"></i>

          </div>

          <h5>
            Farmer Marketplace
          </h5>

          <p>

            Farmers can list products and buyers can
            discover agricultural products in one marketplace.

          </p>

        </div>

      </div>



      <!-- CARD 6 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-bar-chart-line"></i>

          </div>

          <h5>
            Market Prices
          </h5>

          <p>

            View market price records with market name,
            date and source for better transparency.

          </p>

        </div>

      </div>



      <!-- CARD 7 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-bank"></i>

          </div>

          <h5>
            Government Schemes
          </h5>

          <p>

            Keep agricultural scheme information,
            eligibility, documents and official sources together.

          </p>

        </div>

      </div>



      <!-- CARD 8 -->

      <div class="col-md-6 col-lg-3">

        <div class="feature-card">

          <div class="feature-icon">

            <i class="bi bi-person-workspace"></i>

          </div>

          <h5>
            Expert Guidance
          </h5>

          <p>

            Farmers can submit questions and receive
            guidance through the agriculture expert module.

          </p>

        </div>

      </div>


    </div>

  </div>

</section>



<!-- =========================================
     DASHBOARD
========================================= -->

<section
  class="section preview-section"
  id="market"
>

  <div class="container">

    <div class="row align-items-center g-5">


      <div class="col-lg-5">

        <div class="section-label mb-2">

          A connected farming experience

        </div>


        <h2 class="section-title">

          See your farming information at a glance.

        </h2>


        <p
          class="mt-3 text-secondary"
          style="line-height:1.8"
        >

          The AgroSmart dashboard is designed to keep
          important actions close: crops, products,
          enquiries, complaints, market information
          and expert support.

        </p>


        <div class="mt-4">


          <div class="d-flex gap-3 mb-3">

            <i
              class="bi bi-check2-circle text-success fs-4"
            ></i>

            <div>

              <strong>
                Farmer-friendly navigation
              </strong>

              <br>

              <span class="text-secondary">
                Simple actions and clear information.
              </span>

            </div>

          </div>



          <div class="d-flex gap-3 mb-3">

            <i
              class="bi bi-check2-circle text-success fs-4"
            ></i>

            <div>

              <strong>
                Role-based dashboards
              </strong>

              <br>

              <span class="text-secondary">
                Farmer, buyer, expert and admin workflows.
              </span>

            </div>

          </div>



          <div class="d-flex gap-3">

            <i
              class="bi bi-check2-circle text-success fs-4"
            ></i>

            <div>

              <strong>
                Responsive design
              </strong>

              <br>

              <span class="text-secondary">
                Works across desktop, tablet and mobile.
              </span>

            </div>

          </div>


        </div>

      </div>



      <div class="col-lg-7">

        <div class="dashboard-window">


          <div class="window-bar">

            <span class="dot"></span>

            <span class="dot"></span>

            <span class="dot"></span>

            <span
              class="ms-2 small text-secondary"
            >
              AgroSmart / Farmer Dashboard
            </span>

          </div>


          <div class="dash-body">


            <div class="row g-3 mb-3">


              <div class="col-6 col-md-3">

                <div class="mini-stat">

                  <i class="bi bi-flower1"></i>

                  <strong>06</strong>

                  <small>
                    My Crops
                  </small>

                </div>

              </div>


              <div class="col-6 col-md-3">

                <div class="mini-stat">

                  <i class="bi bi-box-seam"></i>

                  <strong>12</strong>

                  <small>
                    Products
                  </small>

                </div>

              </div>


              <div class="col-6 col-md-3">

                <div class="mini-stat">

                  <i class="bi bi-envelope"></i>

                  <strong>08</strong>

                  <small>
                    Enquiries
                  </small>

                </div>

              </div>


              <div class="col-6 col-md-3">

                <div class="mini-stat">

                  <i class="bi bi-chat-left-text"></i>

                  <strong>02</strong>

                  <small>
                    Questions
                  </small>

                </div>

              </div>


            </div>


            <div class="chart">

              <svg
                viewBox="0 0 700 190"
                preserveAspectRatio="none"
              >

                <polyline
                  points="0,150 90,128 160,142 240,92 320,112 400,62 475,85 550,50 630,70 700,28"
                  fill="none"
                  stroke="#198754"
                  stroke-width="5"
                />

                <polyline
                  points="0,150 90,128 160,142 240,92 320,112 400,62 475,85 550,50 630,70 700,28 700,190 0,190"
                  fill="#198754"
                  opacity=".10"
                  stroke="none"
                />

              </svg>

            </div>

          </div>

        </div>

      </div>

    </div>

  </div>

</section>



<!-- =========================================
     HOW IT WORKS
========================================= -->

<section
  class="section"
  id="how"
>

  <div class="container">


    <div class="text-center mb-5">

      <div class="section-label mb-2">

        Simple workflow

      </div>


      <h2 class="section-title">

        How AgroSmart works

      </h2>


      <p class="section-subtitle">

        A simple flow designed for real-world agricultural use.

      </p>

    </div>



    <div class="row g-5">


      <div class="col-md-3 step">

        <div class="step-number">
          01
        </div>

        <h5>
          Create Profile
        </h5>

        <p>

          Register as a farmer, buyer or expert
          and create your profile.

        </p>

      </div>



      <div class="col-md-3 step">

        <div class="step-number">
          02
        </div>

        <h5>
          Use Smart Tools
        </h5>

        <p>

          Explore crop information, recommendations,
          weather and disease guidance.

        </p>

      </div>



      <div class="col-md-3 step">

        <div class="step-number">
          03
        </div>

        <h5>
          Connect
        </h5>

        <p>

          List agricultural products, discover products
          and send buyer enquiries.

        </p>

      </div>



      <div class="col-md-3 step">

        <div class="step-number">
          04
        </div>

        <h5>
          Make Decisions
        </h5>

        <p>

          Use organized information and expert guidance
          to support farming decisions.

        </p>

      </div>


    </div>

  </div>

</section>



<!-- =========================================
     CTA
========================================= -->

<div
  class="container"
  id="start"
>

  <section class="cta">


    <div class="section-label text-white-50">

      Agri technology for everyone

    </div>


    <h2 class="display-5 mt-2">

      One platform. Many farming needs.

    </h2>


    <p>

      AgroSmart is designed as a BCA field project
      that demonstrates authentication, database
      relationships, CRUD operations, APIs, dashboards
      and real-world problem solving.

    </p>


    <a
      href="#home"
      class="btn"
    >

      Start Exploring

      <i class="bi bi-arrow-up-right ms-1"></i>

    </a>


  </section>

</div>



<!-- =========================================
     FOOTER
========================================= -->

<footer>

  <div class="container">

    <div class="row g-5">


      <div class="col-lg-5">

        <a
          class="brand text-decoration-none"
          href="#home"
        >

          <i class="bi bi-leaf-fill me-2"></i>

          AgroSmart

        </a>


        <p
          class="mt-3"
          style="max-width:440px;line-height:1.8"
        >

          Smart Agriculture Assistant &
          Farmer Market Portal —
          connecting agricultural information,
          market access and expert guidance.

        </p>

      </div>



      <div class="col-6 col-lg-2">

        <h6>
          Platform
        </h6>

        <a href="#features">
          Features
        </a>

        <a href="#market">
          Marketplace
        </a>

        <a href="#how">
          How It Works
        </a>

      </div>



      <div class="col-6 col-lg-2">

        <h6>
          Services
        </h6>

        <a href="#features">
          Crop Guide
        </a>

        <a href="#features">
          Weather
        </a>

        <a href="#features">
          Market Prices
        </a>

      </div>



      <div class="col-lg-3">

        <h6>
          Project
        </h6>

        <p class="small mb-0">

          BCA Field Project

          <br>

          HTML5 • CSS3 • JavaScript • Bootstrap 5

          <br>

          PHP • MySQL • Chart.js

        </p>

      </div>


    </div>


    <div class="copyright text-center">

      © 2026 AgroSmart.
      BCA Field Project.

    </div>

  </div>

</footer>



<!-- =========================================
     BOOTSTRAP JS
========================================= -->

<script
  src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
></script>


<script>

  /* =========================================
     ACTIVE NAVIGATION
  ========================================= */

  const sections =
    document.querySelectorAll(
      "section, header"
    );

  const links =
    document.querySelectorAll(
      ".nav-link"
    );


  window.addEventListener(
    "scroll",
    () => {

      let current = "home";


      sections.forEach(
        section => {

          const top =
            section.offsetTop - 130;


          if (
            window.scrollY >= top
          ) {

            current =
              section.id || current;

          }

        }
      );


      links.forEach(
        link => {

          link.classList.toggle(
            "active",

            link.getAttribute("href")
              === "#" + current
          );

        }
      );

    }
  );



  /* =========================================
     SCROLL REVEAL
  ========================================= */

  const observer =
    new IntersectionObserver(
      entries => {

        entries.forEach(
          entry => {

            if (
              entry.isIntersecting
            ) {

              entry.target.style.animation =
                "rise .75s ease both";

              observer.unobserve(
                entry.target
              );

            }

          }
        );

      },
      {
        threshold: 0.12
      }
    );


  document
    .querySelectorAll(
      ".section-title, .step"
    )
    .forEach(
      element =>
        observer.observe(element)
    );

</script>


</body>
</html>
