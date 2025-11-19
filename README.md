# updated-design
Updated design for the WEDE part2 design with CSS styles added.




<!DOCTYPE html>
<html lang="en-ZA">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Legends Barber Shop | Professional Haircuts & Grooming in Johannesburg</title>
    <meta name="description" content="Legends Barber Shop Johannesburg - Premium haircuts, beard trims & grooming services. Special student & pensioner discounts. Book your appointment online today.">
    <meta name="keywords" content="barber shop Johannesburg, haircut, beard trim, grooming services, student discount, pensioner discount, professional barber, men's grooming">
    <meta name="author" content="Legends Barber Shop">
    <meta name="robots" content="index, follow">
    <meta name="googlebot" content="index, follow">
    
    <!-- Open Graph Meta Tags -->
    <meta property="og:title" content="Legends Barber Shop | Premium Barber Services in Johannesburg">
    <meta property="og:description" content="Professional haircuts, beard trims & grooming services with special discounts for students and pensioners.">
    <meta property="og:type" content="website">
    <meta property="og:url" content="https://www.legendsbarbershop.co.za">
    <meta property="og:image" content="https://images.unsplash.com/photo-1585747860715-2ba37e788b70?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80">
    <meta property="og:site_name" content="Legends Barber Shop">
    
    <!-- Twitter Card Meta Tags -->
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Legends Barber Shop | Professional Barber Services">
    <meta name="twitter:description" content="Premium haircuts & grooming services in Johannesburg with student & pensioner discounts.">
    <meta name="twitter:image" content="https://images.unsplash.com/photo-1585747860715-2ba37e788b70?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80">
    
    <!-- Local Business Schema -->
    <script type="application/ld+json">
    {
        "@context": "https://schema.org",
        "@type": "BarberShop",
        "name": "Legends Barber Shop",
        "description": "Professional barber shop offering premium haircuts, beard trims and grooming services in Johannesburg",
        "url": "https://www.legendsbarbershop.co.za",
        "telephone": "+27-11-123-4567",
        "address": {
            "@type": "PostalAddress",
            "streetAddress": "123 Barber Street",
            "addressLocality": "Johannesburg",
            "addressCountry": "ZA"
        },
        "geo": {
            "@type": "GeoCoordinates",
            "latitude": "-26.2041",
            "longitude": "28.0473"
        },
        "openingHours": [
            "Mo-Fr 08:00-19:00",
            "Sa 08:00-17:00",
            "Su 09:00-14:00"
        ],
        "priceRange": "R100-R350",
        "areaServed": "Johannesburg and surrounding areas"
    }
    </script>
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" />
    <link rel="canonical" href="https://www.legendsbarbershop.co.za">
    
    <style>
        /* CSS Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            line-height: 1.6;
            color: #333;
            background-color: #f9f9f9;
            overflow-x: hidden;
        }
        
        a {
            text-decoration: none;
            color: inherit;
            transition: all 0.3s ease;
        }
        
        ul, ol {
            list-style: none;
        }
        
        img {
            max-width: 100%;
            height: auto;
            display: block;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 15px;
        }
        
        .btn {
            display: inline-block;
            background: linear-gradient(135deg, #d4af37, #b8941f);
            color: #000;
            padding: 12px 30px;
            border: none;
            border-radius: 30px;
            cursor: pointer;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(212, 175, 55, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(212, 175, 55, 0.4);
        }
        
        section {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
            position: relative;
        }
        
        .section-title h1,
        .section-title h2 {
            font-size: 2.5rem;
            color: #222;
            display: inline-block;
            padding-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }
        
        .section-title h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 4px;
            background: #d4af37;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            border-radius: 2px;
        }
        
        /* Header Styles */
        header {
            background: rgba(34, 34, 34, 0.95);
            color: #fff;
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
        }
        
        header.scrolled {
            padding: 15px 0;
            background: rgba(34, 34, 34, 0.98);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            font-size: 2rem;
            font-weight: 700;
            color: #d4af37;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            margin-right: 10px;
            font-size: 2.2rem;
        }
        
        .logo span {
            color: #fff;
        }
        
        nav ul {
            display: flex;
        }
        
        nav ul li {
            margin-left: 30px;
            position: relative;
        }
        
        nav ul li a {
            font-weight: 600;
            font-size: 1.1rem;
            padding: 5px 0;
        }
        
        nav ul li a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 3px;
            background: #d4af37;
            bottom: -5px;
            left: 0;
            transition: width 0.3s ease;
        }
        
        nav ul li a:hover:after, 
        nav ul li a.active:after {
            width: 100%;
        }
        
        nav ul li a:hover, 
        nav ul li a.active {
            color: #d4af37;
        }
        
        .mobile-menu {
            display: none;
            font-size: 1.8rem;
            cursor: pointer;
            color: #d4af37;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1585747860715-2ba37e788b70?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80') no-repeat center center/cover;
            height: 100vh;
            display: flex;
            align-items: center;
            text-align: center;
            color: #fff;
        }
        
        .hero-content {
            max-width: 800px;
            margin: 0 auto;
            animation: fadeIn 1.5s ease;
        }
        
        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 3px;
            text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.5);
        }
        
        .hero p {
            font-size: 1.3rem;
            margin-bottom: 40px;
            line-height: 1.8;
        }
        
        .hero-btns {
            display: flex;
            justify-content: center;
            gap: 20px;
        }
        
        .btn-secondary {
            background: transparent;
            border: 2px solid #d4af37;
            color: #d4af37;
        }
        
        .btn-secondary:hover {
            background: #d4af37;
            color: #000;
        }
        
        /* About Section */
        .about {
            background: #fff;
        }
        
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text h2 {
            font-size: 2rem;
            margin-bottom: 20px;
            color: #222;
        }
        
        .about-text p {
            margin-bottom: 20px;
            color: #555;
        }
        
        .about-features {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
            margin-top: 30px;
        }
        
        .feature-item {
            display: flex;
            align-items: center;
        }
        
        .feature-item i {
            color: #d4af37;
            font-size: 1.5rem;
            margin-right: 15px;
        }
        
        .about-image {
            flex: 1;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            position: relative;
        }
        
        .about-image:before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            border: 5px solid #d4af37;
            border-radius: 10px;
            top: -20px;
            left: -20px;
            z-index: -1;
        }
        
        .about-image img {
            width: 100%;
            height: auto;
            transition: transform 0.5s ease;
        }
        
        .about-image:hover img {
            transform: scale(1.05);
        }
        
        /* Services Section */
        .services {
            background: #f5f5f5;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background: #fff;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
        }
        
        .service-icon {
            background: linear-gradient(135deg, #d4af37, #b8941f);
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            color: #000;
        }
        
        .service-content {
            padding: 25px;
            text-align: center;
        }
        
        .service-content h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #222;
        }
        
        .service-content p {
            margin-bottom: 20px;
            color: #666;
        }
        
        .price {
            font-weight: 700;
            color: #d4af37;
            font-size: 1.5rem;
            display: block;
        }
        
        /* Packages Section */
        .packages {
            background: #fff;
        }
        
        .packages-content {
            text-align: center;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .packages-content p {
            font-size: 1.3rem;
            margin-bottom: 40px;
            color: #555;
            line-height: 1.8;
        }
        
        .benefits-list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 40px;
        }
        
        .benefit-item {
            background: #f9f9f9;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: transform 0.3s ease;
        }
        
        .benefit-item:hover {
            transform: translateY(-5px);
        }
        
        .benefit-item i {
            font-size: 2.5rem;
            color: #d4af37;
            margin-bottom: 15px;
        }
        
        .benefit-item h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: #222;
        }
        
        /* Contact Section */
        .contact {
            background: #f5f5f5;
        }
        
        .contact-container {
            display: flex;
            gap: 50px;
        }
        
        .contact-info {
            flex: 1;
        }
        
        .contact-info h2 {
            font-size: 1.8rem;
            margin-bottom: 20px;
            color: #222;
        }
        
        .contact-details {
            margin-bottom: 30px;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 25px;
        }
        
        .contact-item i {
            background: #d4af37;
            color: #000;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            font-size: 1.2rem;
        }
        
        .contact-form {
            flex: 1;
            background: #fff;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #333;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 1rem;
            transition: border 0.3s ease;
        }
        
        .form-control:focus {
            border-color: #d4af37;
            outline: none;
        }
        
        textarea.form-control {
            height: 150px;
            resize: vertical;
        }
        
        /* Footer */
        footer {
            background: #222;
            color: #fff;
            padding: 70px 0 30px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 1.4rem;
            margin-bottom: 25px;
            color: #d4af37;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3:after {
            content: '';
            position: absolute;
            width: 50px;
            height: 3px;
            background: #d4af37;
            bottom: 0;
            left: 0;
            border-radius: 2px;
        }
        
        .footer-column p {
            margin-bottom: 20px;
            color: #bbb;
            line-height: 1.8;
        }
        
        .social-links {
            display: flex;
            gap: 15px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: #333;
            border-radius: 50%;
            transition: all 0.3s ease;
        }
        
        .social-links a:hover {
            background: #d4af37;
            transform: translateY(-3px);
            color: #000;
        }
        
        .footer-links li {
            margin-bottom: 12px;
        }
        
        .footer-links a {
            color: #bbb;
            transition: color 0.3s ease;
            display: flex;
            align-items: center;
        }
        
        .footer-links a i {
            margin-right: 10px;
            color: #d4af37;
        }
        
        .footer-links a:hover {
            color: #d4af37;
            padding-left: 5px;
        }
        
        .opening-hours li {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            color: #bbb;
            padding-bottom: 10px;
            border-bottom: 1px solid #333;
        }
        
        .opening-hours li:last-child {
            border-bottom: none;
        }
        
        .copyright {
            text-align: center;
            padding-top: 30px;
            border-top: 1px solid #444;
            color: #bbb;
            font-size: 0.9rem;
        }
        
        /* NEW: Interactive Elements Styles */
        
        /* Tabs */
        .tabs {
            margin: 30px 0;
        }
        
        .tab-header {
            display: flex;
            border-bottom: 2px solid #e9ecef;
            margin-bottom: 20px;
        }
        
        .tab-link {
            padding: 12px 24px;
            background: none;
            border: none;
            cursor: pointer;
            font-size: 1rem;
            font-weight: 600;
            color: #666;
            border-bottom: 3px solid transparent;
            transition: all 0.3s ease;
        }
        
        .tab-link.active {
            color: #d4af37;
            border-bottom-color: #d4af37;
        }
        
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        .tab-content.active {
            display: block;
        }
        
        /* Accordion */
        .accordion {
            margin: 30px 0;
        }
        
        .accordion-item {
            border: 1px solid #e9ecef;
            border-radius: 5px;
            margin-bottom: 10px;
            overflow: hidden;
        }
        
        .accordion-header {
            padding: 15px 20px;
            background: #f8f9fa;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-weight: 600;
            transition: background 0.3s ease;
        }
        
        .accordion-header:hover {
            background: #e9ecef;
        }
        
        .accordion-header.active {
            background: #d4af37;
            color: #000;
        }
        
        .accordion-content {
            padding: 0 20px;
            max-height: 0;
            overflow: hidden;
            transition: all 0.3s ease;
        }
        
        .accordion-content.active {
            padding: 20px;
            max-height: 500px;
        }
        
        /* Gallery */
        .gallery {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin: 30px 0;
        }
        
        .gallery-item {
            position: relative;
            border-radius: 8px;
            overflow: hidden;
            cursor: pointer;
            aspect-ratio: 1;
        }
        
        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }
        
        .gallery-item:hover img {
            transform: scale(1.1);
        }
        
        /* Lightbox */
        .lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.9);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }
        
        .lightbox.active {
            display: flex;
            animation: fadeIn 0.3s ease;
        }
        
        .lightbox-content {
            max-width: 90%;
            max-height: 90%;
            position: relative;
        }
        
        .lightbox-content img {
            width: 100%;
            height: auto;
            border-radius: 8px;
        }
        
        .lightbox-close {
            position: absolute;
            top: -40px;
            right: 0;
            background: none;
            border: none;
            color: white;
            font-size: 2rem;
            cursor: pointer;
        }
        
        .lightbox-nav {
            position: absolute;
            top: 50%;
            width: 100%;
            display: flex;
            justify-content: space-between;
            transform: translateY(-50%);
        }
        
        .lightbox-prev,
        .lightbox-next {
            background: rgba(212, 175, 55, 0.8);
            border: none;
            color: #000;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            font-size: 1.5rem;
            cursor: pointer;
            margin: 0 20px;
            transition: background 0.3s ease;
        }
        
        .lightbox-prev:hover,
        .lightbox-next:hover {
            background: #d4af37;
        }
        
        /* Map */
        #map {
            height: 400px;
            border-radius: 10px;
            margin: 30px 0;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
        }
        
        /* Search */
        .search-container {
            margin: 30px 0;
            position: relative;
        }
        
        .search-input {
            width: 100%;
            padding: 15px 50px 15px 20px;
            border: 2px solid #e9ecef;
            border-radius: 30px;
            font-size: 1rem;
            transition: border 0.3s ease;
        }
        
        .search-input:focus {
            border-color: #d4af37;
            outline: none;
        }
        
        .search-icon {
            position: absolute;
            right: 20px;
            top: 50%;
            transform: translateY(-50%);
            color: #666;
            font-size: 1.2rem;
        }
        
        /* Animations */
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        @keyframes slideDown {
            from { 
                opacity: 0;
                transform: translateY(-20px);
            }
            to { 
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .animated {
            animation: slideDown 0.6s ease;
        }
        
        /* SEO Optimized Elements */
        .breadcrumb {
            background: #f8f9fa;
            padding: 15px 0;
            margin-bottom: 30px;
        }
        
        .breadcrumb ul {
            display: flex;
            flex-wrap: wrap;
        }
        
        .breadcrumb li {
            margin-right: 10px;
        }
        
        .breadcrumb li:not(:last-child):after {
            content: '/';
            margin-left: 10px;
            color: #666;
        }
        
        .breadcrumb a {
            color: #666;
        }
        
        .breadcrumb a:hover {
            color: #d4af37;
        }
        
        /* Performance Optimizations */
        .lazy-load {
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        
        .lazy-load.loaded {
            opacity: 1;
        }
        
        /* Security Badge */
        .security-badge {
            display: inline-block;
            background: #27ae60;
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 0.8rem;
            margin-left: 10px;
        }
        
        /* Responsive Design */
        @media (max-width: 992px) {
            .about-content, .contact-container {
                flex-direction: column;
            }
            
            .about-image, .about-text {
                flex: none;
                width: 100%;
            }
            
            .about-image {
                order: -1;
                margin-bottom: 40px;
            }
            
            .about-image:before {
                display: none;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
            
            .tab-header {
                flex-direction: column;
            }
            
            .tab-link {
                text-align: center;
            }
        }
        
        @media (max-width: 768px) {
            nav ul {
                display: none;
                position: absolute;
                top: 70px;
                left: 0;
                width: 100%;
                background: #222;
                flex-direction: column;
                text-align: center;
                padding: 20px 0;
                box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
            }
            
            nav ul.active {
                display: flex;
            }
            
            nav ul li {
                margin: 15px 0;
            }
            
            .mobile-menu {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1.1rem;
            }
            
            .hero-btns {
                flex-direction: column;
                align-items: center;
                gap: 15px;
            }
            
            section {
                padding: 60px 0;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
            
            .gallery {
                grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            }
        }
        
        @media (max-width: 576px) {
            .hero h1 {
                font-size: 1.8rem;
            }
            
            .about-features, .benefits-list {
                grid-template-columns: 1fr;
            }
            
            .btn {
                padding: 10px 25px;
                font-size: 0.9rem;
            }
            
            .gallery {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header id="header">
        <div class="container header-container">
            <div class="logo">
                <i class="fas fa-cut"></i>
                Legends <span>Barber Shop</span>
                <span class="security-badge">Secure</span>
            </div>
            <nav>
                <div class="mobile-menu">
                    <i class="fas fa-bars"></i>
                </div>
                <ul>
                    <li><a href="#home" class="active">Home</a></li>
                    <li><a href="#about">About</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#packages">Packages</a></li>
                    <li><a href="#gallery">Gallery</a></li>
                    <li><a href="#contact">Contact Us</a></li>
                    <li><a href="#appointment" class="btn">Appointment</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Breadcrumb Navigation -->
    <div class="breadcrumb">
        <div class="container">
            <ul>
                <li><a href="#home">Home</a></li>
                <li><span>Current Page</span></li>
            </ul>
        </div>
    </div>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container hero-content">
            <h1>Legends Barber Shop Johannesburg</h1>
            <p>Experience premium grooming services with our expert barbers. We offer special packages for students and pensioners with no queues and maximum comfort.</p>
            <div class="hero-btns">
                <a href="#appointment" class="btn">Book an Appointment</a>
                <a href="#packages" class="btn btn-secondary">View Packages</a>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section class="about" id="about">
        <div class="container">
            <div class="section-title">
                <h2>About Legends Barber Shop</h2>
            </div>
            
            <!-- Tabs -->
            <div class="tabs">
                <div class="tab-header">
                    <button class="tab-link active" data-tab="tab1">Our Story</button>
                    <button class="tab-link" data-tab="tab2">Our Team</button>
                    <button class="tab-link" data-tab="tab3">Our Mission</button>
                </div>
                <div class="tab-content active" id="tab1">
                    <h3>Your Neighborhood Barbers Since 2010</h3>
                    <p>Legends Barber Shop (PTY) LTD has independent owner store & franchise operators. We are a registered business in South Africa, dedicated to providing exceptional grooming services to our community.</p>
                    <p>Our barbers are highly skilled professionals who stay updated with the latest trends and techniques to ensure you get the perfect cut every time.</p>
                </div>
                <div class="tab-content" id="tab2">
                    <h3>Meet Our Expert Barbers</h3>
                    <p>Our team consists of certified barbers with years of experience in traditional and modern grooming techniques. Each barber undergoes continuous training to stay ahead of industry trends.</p>
                    <p>We pride ourselves on creating a welcoming environment where every client feels like family.</p>
                </div>
                <div class="tab-content" id="tab3">
                    <h3>Our Commitment to Excellence</h3>
                    <p>We're committed to providing the highest quality grooming services while maintaining affordable prices. Our mission is to make premium barber services accessible to everyone in our community.</p>
                    <p>We believe that a great haircut should be an experience, not just a service.</p>
                </div>
            </div>

            <div class="about-content">
                <div class="about-text">
                    <div class="about-features">
                        <div class="feature-item">
                            <i class="fas fa-check-circle"></i>
                            <span>Expert Barbers</span>
                        </div>
                        <div class="feature-item">
                            <i class="fas fa-check-circle"></i>
                            <span>Premium Products</span>
                        </div>
                        <div class="feature-item">
                            <i class="fas fa-check-circle"></i>
                            <span>Modern Facilities</span>
                        </div>
                        <div class="feature-item">
                            <i class="fas fa-check-circle"></i>
                            <span>Customer Satisfaction</span>
                        </div>
                    </div>
                    <a href="#contact" class="btn" style="margin-top: 20px;">Visit Us Today</a>
                </div>
                <div class="about-image">
                    <img 
                        src="https://images.unsplash.com/photo-1599351431202-1e0f0137899a?ixlib=rb-4.0.3&auto=format&fit=crop&w=1350&q=80" 
                        alt="Legends Barber Shop Interior - Professional barber chairs and grooming station"
                        class="lazy-load"
                    >
                </div>
            </div>
        </div>
    </section>

    <!-- Services Section -->
    <section class="services" id="services">
        <div class="container">
            <div class="section-title">
                <h2>Our Barber Services</h2>
            </div>

            <!-- Search Functionality -->
            <div class="search-container">
                <input type="text" class="search-input" id="serviceSearch" placeholder="Search for services...">
                <i class="fas fa-search search-icon"></i>
            </div>

            <!-- Accordion for Service Details -->
            <div class="accordion">
                <div class="accordion-item">
                    <div class="accordion-header">
                        <span>View All Service Details</span>
                        <i class="fas fa-chevron-down"></i>
                    </div>
                    <div class="accordion-content">
                        <p>Explore our complete range of grooming services. Each service is performed by our certified barbers using premium products and equipment.</p>
                    </div>
                </div>
            </div>

            <div class="services-grid" id="servicesGrid">
                <!-- Services will be dynamically loaded here -->
            </div>
        </div>
    </section>

    <!-- Packages Section -->
    <section class="packages" id="packages">
        <div class="container">
            <div class="section-title">
                <h2>Special Barber Packages</h2>
            </div>
            <div class="packages-content">
                <p><b>We offer exclusive packages for Students and Pensioners with special discounts and benefits.</b></p>
                
                <div class="benefits-list">
                    <div class="benefit-item">
                        <i class="fas fa-clock"></i>
                        <h3>Haircut under 60 minutes</h3>
                        <p>Quick and efficient service without compromising on quality.</p>
                    </div>
                    <div class="benefit-item">
                        <i class="fas fa-users"></i>
                        <h3>No queue</h3>
                        <p>Appointment-based system to minimize your waiting time.</p>
                    </div>
                    <div class="benefit-item">
                        <i class="fas fa-graduation-cap"></i>
                        <h3>Student Discounts</h3>
                        <p>Special rates for students with valid student ID cards.</p>
                    </div>
                    <div class="benefit-item">
                        <i class="fas fa-user-friends"></i>
                        <h3>Pensioners Discounts</h3>
                        <p>Discounted services for our respected senior citizens.</p>
                    </div>
                    <div class="benefit-item">
                        <i class="fas fa-spray-can"></i>
                        <h3>Clean Barbershop</h3>
                        <p>Hygienic and sanitized environment for your safety.</p>
                    </div>
                    <div class="benefit-item">
                        <i class="fas fa-file-contract"></i>
                        <h3>Monthly Contracts</h3>
                        <p>Subscribe to our monthly plans for regular grooming needs.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Gallery Section -->
    <section class="gallery-section" id="gallery">
        <div class="container">
            <div class="section-title">
                <h2>Our Work Gallery</h2>
            </div>
            <div class="gallery" id="imageGallery">
                <!-- Gallery images will be dynamically loaded -->
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Contact Our Barber Shop</h2>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <h2>Get In Touch</h2>
                    <div class="contact-details">
                        <div class="contact-item">
                            <i class="fas fa-map-marker-alt"></i>
                            <div>
                                <h3>Our Location</h3>
                                <p>123 Barber Street, Johannesburg, South Africa</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-phone"></i>
                            <div>
                                <h3>Phone Number</h3>
                                <p>+27 11 123 4567</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-envelope"></i>
                            <div>
                                <h3>Email Address</h3>
                                <p>info@legendsbarbershop.co.za</p>
                            </div>
                        </div>
                        <div class="contact-item">
                            <i class="fas fa-clock"></i>
                            <div>
                                <h3>Opening Hours</h3>
                                <p>Mon-Fri: 8am-7pm, Sat: 8am-5pm, Sun: 9am-2pm</p>
                            </div>
                        </div>
                    </div>

                    <!-- Interactive Map -->
                    <div id="map"></div>

                    <div class="social-links">
                        <a href="#" aria-label="Follow us on Facebook"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" aria-label="Follow us on Instagram"><i class="fab fa-instagram"></i></a>
                        <a href="#" aria-label="Follow us on Twitter"><i class="fab fa-twitter"></i></a>
                        <a href="#" aria-label="Contact us on WhatsApp"><i class="fab fa-whatsapp"></i></a>
                    </div>
                </div>
                <div class="contact-form">
                    <h2>Book an Appointment</h2>
                    <form id="appointment">
                        <div class="form-group">
                            <label for="name">Your Name</label>
                            <input type="text" id="name" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="email">Your Email</label>
                            <input type="email" id="email" class="form-control" required>
                        </div>
                        <div class="form-group">
                            <label for="phone">Phone Number</label>
                            <input type="tel" id="phone" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="service">Service Interested In</label>
                            <select id="service" class="form-control">
                                <option value="">Select a service</option>
                                <!-- Options will be dynamically loaded -->
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="date">Preferred Date</label>
                            <input type="date" id="date" class="form-control">
                        </div>
                        <div class="form-group">
                            <label for="message">Additional Message</label>
                            <textarea id="message" class="form-control"></textarea>
                        </div>
                        <button type="submit" class="btn">Book Appointment</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Lightbox -->
    <div class="lightbox" id="lightbox">
        <button class="lightbox-close">&times;</button>
        <div class="lightbox-nav">
            <button class="lightbox-prev">&lt;</button>
            <button class="lightbox-next">&gt;</button>
        </div>
        <div class="lightbox-content">
            <img src="" alt="" id="lightbox-image">
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>Legends Barber Shop</h3>
                    <p>Providing premium barber services with traditional techniques and modern style. Registered business in South Africa.</p>
                    <div class="social-links">
                        <a href="#" aria-label="Follow us on Facebook"><i class="fab fa-facebook-f"></i></a>
                        <a href="#" aria-label="Follow us on Instagram"><i class="fab fa-instagram"></i></a>
                        <a href="#" aria-label="Follow us on Twitter"><i class="fab fa-twitter"></i></a>
                        <a href="#" aria-label="Contact us on WhatsApp"><i class="fab fa-whatsapp"></i></a>
                    </div>
                </div>
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul class="footer-links">
                        <li><a href="#home"><i class="fas fa-chevron-right"></i> Home</a></li>
                        <li><a href="#about"><i class="fas fa-chevron-right"></i> About Us</a></li>
                        <li><a href="#services"><i class="fas fa-chevron-right"></i> Services</a></li>
                        <li><a href="#packages"><i class="fas fa-chevron-right"></i> Packages</a></li>
                        <li><a href="#contact"><i class="fas fa-chevron-right"></i> Contact</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Our Services</h3>
                    <ul class="footer-links">
                        <li><a href="#services"><i class="fas fa-chevron-right"></i> Classic Haircut</a></li>
                        <li><a href="#services"><i class="fas fa-chevron-right"></i> Beard Trim & Shape</a></li>
                        <li><a href="#services"><i class="fas fa-chevron-right"></i> Hot Towel Shave</a></li>
                        <li><a href="#services"><i class="fas fa-chevron-right"></i> Hair & Beard Combo</a></li>
                        <li><a href="#services"><i class="fas fa-chevron-right"></i> Hair Coloring</a></li>
                    </ul>
                </div>
                <div class="footer-column">
                    <h3>Opening Hours</h3>
                    <ul class="opening-hours">
                        <li><span>Monday - Friday</span> <span>8:00 - 19:00</span></li>
                        <li><span>Saturday</span> <span>8:00 - 17:00</span></li>
                        <li><span>Sunday</span> <span>9:00 - 14:00</span></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>© 2023 Legends Barber Shop (PTY) LTD | All Rights Reserved. | <a href="/privacy-policy.html" style="color: #d4af37;">Privacy Policy</a> | <a href="/terms.html" style="color: #d4af37;">Terms of Service</a></p>
            </div>
        </div>
    </footer>

    <!-- JavaScript Libraries -->
    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>

    <script>
        // Service Data
        const servicesData = [
            {
                id: 1,
                name: 'Classic Haircut',
                description: 'Professional haircut with precision styling and finishing touches. Our barbers use the latest techniques to give you the perfect look.',
                price: 150,
                duration: '30-45 min',
                category: 'haircut',
                icon: 'cut'
            },
            {
                id: 2,
                name: 'Beard Trim & Shape',
                description: 'Expert beard grooming and shaping to enhance your look. Includes conditioning and styling.',
                price: 80,
                duration: '20-30 min',
                category: 'beard',
                icon: 'air-freshener'
            },
            {
                id: 3,
                name: 'Hot Towel Shave',
                description: 'Traditional straight razor shave with hot towels for ultimate relaxation. Includes pre-shave oil and post-shave balm.',
                price: 120,
                duration: '25-35 min',
                category: 'shave',
                icon: 'spa'
            },
            {
                id: 4,
                name: 'Hair & Beard Combo',
                description: 'Complete grooming package including haircut and beard service. Perfect for a full transformation.',
                price: 200,
                duration: '50-60 min',
                category: 'combo',
                icon: 'user'
            },
            {
                id: 5,
                name: 'Hair Coloring',
                description: 'Professional hair coloring services using premium products. Consultation included.',
                price: 250,
                duration: '60-90 min',
                category: 'color',
                icon: 'palette'
            },
            {
                id: 6,
                name: 'Kids Cut',
                description: 'Specialized haircuts for children in a friendly environment. Fun and comfortable experience.',
                price: 100,
                duration: '20-30 min',
                category: 'kids',
                icon: 'child'
            }
        ];

        // Gallery Images
        const galleryImages = [
            {
                src: 'https://images.unsplash.com/photo-1585747860715-2ba37e788b70?w=500',
                alt: 'Barber styling customer hair'
            },
            {
                src: 'https://images.unsplash.com/photo-1599351431202-1e0f0137899a?w=500',
                alt: 'Modern barber shop interior'
            },
            {
                src: 'https://images.unsplash.com/photo-1621605815976-ac25731f4e68?w=500',
                alt: 'Beard trimming service'
            },
            {
                src: 'https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=500',
                alt: 'Professional haircut in progress'
            },
            {
                src: 'https://images.unsplash.com/photo-1567894340317-9603363b12e1?w=500',
                alt: 'Barber tools and equipment'
            },
            {
                src: 'https://images.unsplash.com/photo-1593705114312-a0ee03a3f7d0?w=500',
                alt: 'Customer enjoying hot towel shave'
            }
        ];

        // DOM Content Loaded
        document.addEventListener('DOMContentLoaded', function() {
            initializeTabs();
            initializeAccordion();
            loadServices();
            initializeSearch();
            loadGallery();
            initializeLightbox();
            initializeMap();
            initializeForm();
            initializeAnimations();
        });

        // Tab System
        function initializeTabs() {
            const tabLinks = document.querySelectorAll('.tab-link');
            const tabContents = document.querySelectorAll('.tab-content');

            tabLinks.forEach(link => {
                link.addEventListener('click', function() {
                    const tabId = this.getAttribute('data-tab');
                    
                    // Remove active class from all tabs and contents
                    tabLinks.forEach(l => l.classList.remove('active'));
                    tabContents.forEach(c => c.classList.remove('active'));
                    
                    // Add active class to current tab and content
                    this.classList.add('active');
                    document.getElementById(tabId).classList.add('active');
                });
            });
        }

        // Accordion System
        function initializeAccordion() {
            const accordionHeaders = document.querySelectorAll('.accordion-header');

            accordionHeaders.forEach(header => {
                header.addEventListener('click', function() {
                    const content = this.nextElementSibling;
                    const isActive = this.classList.contains('active');

                    // Close all accordions
                    document.querySelectorAll('.accordion-header').forEach(h => {
                        h.classList.remove('active');
                        h.querySelector('i').classList.remove('fa-chevron-up');
                        h.querySelector('i').classList.add('fa-chevron-down');
                    });
                    document.querySelectorAll('.accordion-content').forEach(c => {
                        c.classList.remove('active');
                    });

                    // Open current accordion if it was closed
                    if (!isActive) {
                        this.classList.add('active');
                        content.classList.add('active');
                        this.querySelector('i').classList.remove('fa-chevron-down');
                        this.querySelector('i').classList.add('fa-chevron-up');
                    }
                });
            });
        }

        // Load Services Dynamically
        function loadServices() {
            const servicesGrid = document.getElementById('servicesGrid');
            const serviceSelect = document.getElementById('service');

            servicesData.forEach(service => {
                // Create service card
                const serviceCard = document.createElement('div');
                serviceCard.className = 'service-card animated';
                serviceCard.setAttribute('data-category', service.category);
                serviceCard.setAttribute('data-name', service.name.toLowerCase());
                
                serviceCard.innerHTML = `
                    <div class="service-icon">
                        <i class="fas fa-${service.icon}"></i>
                    </div>
                    <div class="service-content">
                        <h3>${service.name}</h3>
                        <p>${service.description}</p>
                        <span class="price">R ${service.price}</span>
                        <small>Duration: ${service.duration}</small>
                    </div>
                `;

                servicesGrid.appendChild(serviceCard);

                // Add to form select
                const option = document.createElement('option');
                option.value = service.category;
                option.textContent = service.name;
                serviceSelect.appendChild(option);
            });
        }

        // Search Functionality
        function initializeSearch() {
            const searchInput = document.getElementById('serviceSearch');
            
            searchInput.addEventListener('input', function() {
                const searchTerm = this.value.toLowerCase();
                const serviceCards = document.querySelectorAll('.service-card');

                serviceCards.forEach(card => {
                    const serviceName = card.getAttribute('data-name');
                    const serviceCategory = card.getAttribute('data-category');
                    
                    if (serviceName.includes(searchTerm) || serviceCategory.includes(searchTerm)) {
                        card.style.display = 'block';
                        card.classList.add('animated');
                    } else {
                        card.style.display = 'none';
                    }
                });
            });
        }

        // Gallery System
        function loadGallery() {
            const gallery = document.getElementById('imageGallery');
            
            galleryImages.forEach((image, index) => {
                const galleryItem = document.createElement('div');
                galleryItem.className = 'gallery-item';
                galleryItem.setAttribute('data-index', index);
                
                galleryItem.innerHTML = `
                    <img src="${image.src}" alt="${image.alt}" loading="lazy">
                `;

                galleryItem.addEventListener('click', () => openLightbox(index));
                gallery.appendChild(galleryItem);
            });
        }

        // Lightbox System
        function initializeLightbox() {
            const lightbox = document.getElementById('lightbox');
            const lightboxImage = document.getElementById('lightbox-image');
            const lightboxClose = document.querySelector('.lightbox-close');
            const lightboxPrev = document.querySelector('.lightbox-prev');
            const lightboxNext = document.querySelector('.lightbox-next');

            let currentImageIndex = 0;

            window.openLightbox = function(index) {
                currentImageIndex = index;
                updateLightboxImage();
                lightbox.classList.add('active');
                document.body.style.overflow = 'hidden';
            }

            function updateLightboxImage() {
                const image = galleryImages[currentImageIndex];
                lightboxImage.src = image.src;
                lightboxImage.alt = image.alt;
            }

            function closeLightbox() {
                lightbox.classList.remove('active');
                document.body.style.overflow = 'auto';
            }

            function showNextImage() {
                currentImageIndex = (currentImageIndex + 1) % galleryImages.length;
                updateLightboxImage();
            }

            function showPrevImage() {
                currentImageIndex = (currentImageIndex - 1 + galleryImages.length) % galleryImages.length;
                updateLightboxImage();
            }

            // Event listeners
            lightboxClose.addEventListener('click', closeLightbox);
            lightboxNext.addEventListener('click', showNextImage);
            lightboxPrev.addEventListener('click', showPrevImage);

            // Keyboard navigation
            document.addEventListener('keydown', function(e) {
                if (!lightbox.classList.contains('active')) return;
                
                if (e.key === 'Escape') closeLightbox();
                if (e.key === 'ArrowRight') showNextImage();
                if (e.key === 'ArrowLeft') showPrevImage();
            });

            // Close lightbox when clicking on background
            lightbox.addEventListener('click', function(e) {
                if (e.target === lightbox) closeLightbox();
            });
        }

        // Interactive Map
        function initializeMap() {
            const map = L.map('map').setView([-26.2041, 28.0473], 15);

            L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
                attribution: '© OpenStreetMap contributors'
            }).addTo(map);

            L.marker([-26.2041, 28.0473])
                .addTo(map)
                .bindPopup('<b>Legends Barber Shop</b><br>123 Barber Street, Johannesburg')
                .openPopup();
        }

        // Form Handling
        function initializeForm() {
            const form = document.getElementById('appointment');
            
            form.addEventListener('submit', function(e) {
                e.preventDefault();
                
                const formData = {
                    name: document.getElementById('name').value,
                    email: document.getElementById('email').value,
                    phone: document.getElementById('phone').value,
                    service: document.getElementById('service').value,
                    date: document.getElementById('date').value,
                    message: document.getElementById('message').value
                };

                // Basic validation
                if (!formData.name || !formData.email || !formData.service) {
                    showNotification('Please fill in all required fields', 'error');
                    return;
                }

                // Simulate form submission
                showNotification(`Thank you ${formData.name}! Your appointment request has been received. We will contact you shortly to confirm.`, 'success');
                form.reset();
            });
        }

        // Notification System
        function showNotification(message, type) {
            const notification = document.createElement('div');
            notification.className = `notification ${type}`;
            notification.style.cssText = `
                position: fixed;
                top: 100px;
                right: 20px;
                padding: 15px 20px;
                background: ${type === 'success' ? '#27ae60' : '#e74c3c'};
                color: white;
                border-radius: 5px;
                z-index: 3000;
                animation: slideDown 0.3s ease;
                max-width: 300px;
            `;
            notification.textContent = message;

            document.body.appendChild(notification);

            setTimeout(() => {
                notification.remove();
            }, 5000);
        }

        // Scroll Animations
        function initializeAnimations() {
            const animatedElements = document.querySelectorAll('.service-card, .benefit-item, .gallery-item');

            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('animated');
                        observer.unobserve(entry.target);
                    }
                });
            }, { threshold: 0.1 });

            animatedElements.forEach(el => observer.observe(el));
        }

        // Mobile Menu Toggle
        document.querySelector('.mobile-menu').addEventListener('click', function() {
            document.querySelector('nav ul').classList.toggle('active');
        });
        
        // Header scroll effect
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 100) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
        
        // Smooth Scrolling for Anchor Links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                    
                    // Close mobile menu after clicking a link
                    document.querySelector('nav ul').classList.remove('active');
                }
            });
        });

        // Lazy loading implementation
        const lazyImages = document.querySelectorAll('.lazy-load');
        
        const imageObserver = new IntersectionObserver((entries, observer) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const img = entry.target;
                    img.src = img.dataset.src;
                    img.classList.add('loaded');
                    imageObserver.unobserve(img);
                }
            });
        });

        lazyImages.forEach(img => {
            imageObserver.observe(img);
        });

        // Performance monitoring
        window.addEventListener('load', function() {
            if ('performance' in window) {
                const perfData = window.performance.timing;
                const loadTime = perfData.loadEventEnd - perfData.navigationStart;
                console.log('Page load time:', loadTime + 'ms');
            }
        });
    </script>
</body>
</html>
