```html
<!DOCTYPE html>
<html lang="fr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>City Meal | Saveur Authentique & Fast Food Premium</title>
    <meta name="description" content="City Meal vous propose des plats marocains authentiques et des fast foods savoureux préparés avec des ingrédients frais à Oujda.">
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#ff7a00',
                        dark: {
                            DEFAULT: '#0f0f11',
                            card: '#1a1a1f',
                            lighter: '#25252c'
                        }
                    },
                    fontFamily: {
                        sans: ['Poppins', 'sans-serif'],
                    },
                    boxShadow: {
                        'glow': '0 0 20px rgba(255, 122, 0, 0.3)',
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Styles */
        body {
            background-color: #0f0f11;
            color: #ffffff;
            background-image: radial-gradient(circle at 50% 0%, #1a1a1f 0%, #0f0f11 70%);
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 10px;
        }
        ::-webkit-scrollbar-track {
            background: #0f0f11;
        }
        ::-webkit-scrollbar-thumb {
            background: #333;
            border-radius: 5px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #ff7a00;
        }

        /* Input Number Reset */
        input[type=number]::-webkit-inner-spin-button, 
        input[type=number]::-webkit-outer-spin-button { 
            -webkit-appearance: none; 
            margin: 0; 
        }
        input[type=number] {
            -moz-appearance: textfield;
        }

        /* Scroll Reveal Animation */
        .reveal {
            opacity: 0;
            transform: translateY(30px);
            transition: all 0.8s ease-out;
        }
        .reveal.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* Navbar Sticky Transition */
        #navbar {
            transition: all 0.3s ease;
        }
        #navbar.scrolled {
            background: rgba(15, 15, 17, 0.95);
            backdrop-filter: blur(10px);
            box-shadow: 0 4px 30px rgba(0, 0, 0, 0.5);
            padding-top: 15px;
            padding-bottom: 15px;
        }
    </style>
</head>
<body class="antialiased overflow-x-hidden selection:bg-primary selection:text-white">

    <!-- Navbar -->
    <nav id="navbar" class="fixed w-full z-50 py-5 top-0 border-b border-gray-800/50">
        <div class="container mx-auto px-6 md:px-12 flex justify-between items-center">
            <a href="#" class="text-2xl font-bold tracking-tighter flex items-center gap-2">
                <i class="fa-solid fa-utensils text-primary"></i>
                <span class="text-white">City</span><span class="text-primary">Meal</span>
            </a>
            
            <!-- Desktop Menu -->
            <div class="hidden md:flex items-center gap-8 font-medium">
                <a href="#accueil" class="hover:text-primary transition-colors">Accueil</a>
                <a href="#apropos" class="hover:text-primary transition-colors">À Propos</a>
                <a href="#menu" class="hover:text-primary transition-colors">Menu</a>
                <a href="#contact" class="hover:text-primary transition-colors">Contact</a>
                <a href="#menu" class="px-5 py-2 bg-primary text-white rounded-full hover:bg-orange-600 hover:shadow-glow transition-all transform hover:-translate-y-0.5 font-semibold">
                    Commander
                </a>
            </div>

            <!-- Mobile Toggle -->
            <button id="mobile-menu-btn" class="md:hidden text-2xl text-white focus:outline-none">
                <i class="fa-solid fa-bars"></i>
            </button>
        </div>

        <!-- Mobile Menu Overlay -->
        <div id="mobile-menu" class="hidden absolute top-full left-0 w-full bg-dark-card border-b border-gray-800 shadow-2xl flex-col items-center py-6 gap-6 font-medium">
            <a href="#accueil" class="mobile-link text-lg">Accueil</a>
            <a href="#apropos" class="mobile-link text-lg">À Propos</a>
            <a href="#menu" class="mobile-link text-lg">Menu</a>
            <a href="#contact" class="mobile-link text-lg">Contact</a>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="accueil" class="relative min-h-screen flex items-center justify-center pt-20">
        <!-- Background Image -->
        <div class="absolute inset-0 z-0">
            <img src="https://images.unsplash.com/photo-1550547660-d9450f859349?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80" alt="Delicious Burger" class="w-full h-full object-cover">
            <div class="absolute inset-0 bg-gradient-to-r from-dark via-dark/80 to-dark/40"></div>
        </div>

        <div class="container mx-auto px-6 relative z-10 text-center md:text-left flex flex-col md:flex-row items-center">
            <div class="md:w-1/2 reveal">
                <span class="inline-block py-1 px-3 rounded-full bg-primary/20 text-primary font-semibold text-sm mb-4 border border-primary/30">
                    Bienvenue chez vous
                </span>
                <h1 class="text-5xl md:text-7xl font-extrabold leading-tight mb-6">
                    City <span class="text-primary">Meal</span>
                </h1>
                <p class="text-xl md:text-2xl text-gray-300 mb-10 max-w-lg mx-auto md:mx-0 font-light">
                    Saveur Authentique & Fast Food Premium.
                </p>
                <div class="flex flex-col sm:flex-row gap-4 justify-center md:justify-start">
                    <button onclick="orderNowGlobal()" class="px-8 py-4 bg-primary text-white font-bold rounded-xl hover:bg-orange-600 hover:shadow-glow transition-all transform hover:-translate-y-1 flex items-center justify-center gap-2">
                        <i class="fa-brands fa-whatsapp text-xl"></i> Commander Maintenant
                    </button>
                    <a href="#menu" class="px-8 py-4 bg-dark-lighter border border-gray-700 text-white font-bold rounded-xl hover:bg-gray-800 transition-all flex items-center justify-center">
                        Voir le Menu
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- About Section -->
    <section id="apropos" class="py-24 bg-dark">
        <div class="container mx-auto px-6">
            <div class="text-center max-w-3xl mx-auto mb-16 reveal">
                <h2 class="text-3xl md:text-4xl font-bold mb-6"><span class="text-primary">À Propos</span> de nous</h2>
                <p class="text-gray-400 text-lg leading-relaxed">
                    City Meal vous propose des plats marocains authentiques et des fast foods savoureux préparés avec des ingrédients frais. Une expérience culinaire unique qui allie tradition et modernité pour satisfaire toutes vos envies.
                </p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                <!-- Feature 1 -->
                <div class="bg-dark-card p-8 rounded-2xl border border-gray-800 hover:border-primary/50 transition-colors text-center reveal group">
                    <div class="w-20 h-20 mx-auto bg-dark-lighter rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                        <i class="fa-solid fa-leaf text-3xl text-primary"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Ingrédients Frais</h3>
                    <p class="text-gray-400 text-sm">Sélectionnés chaque jour pour garantir un goût exceptionnel et une qualité irréprochable.</p>
                </div>
                <!-- Feature 2 -->
                <div class="bg-dark-card p-8 rounded-2xl border border-gray-800 hover:border-primary/50 transition-colors text-center reveal group delay-100">
                    <div class="w-20 h-20 mx-auto bg-dark-lighter rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                        <i class="fa-solid fa-bolt text-3xl text-primary"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Service Rapide</h3>
                    <p class="text-gray-400 text-sm">Une préparation efficace pour vous servir rapidement sans compromettre la qualité.</p>
                </div>
                <!-- Feature 3 -->
                <div class="bg-dark-card p-8 rounded-2xl border border-gray-800 hover:border-primary/50 transition-colors text-center reveal group delay-200">
                    <div class="w-20 h-20 mx-auto bg-dark-lighter rounded-full flex items-center justify-center mb-6 group-hover:scale-110 transition-transform duration-300">
                        <i class="fa-solid fa-star text-3xl text-primary"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-3">Qualité Premium</h3>
                    <p class="text-gray-400 text-sm">Des recettes savoureuses élaborées avec passion pour une satisfaction totale.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Menu Section -->
    <section id="menu" class="py-24 bg-[#0a0a0c]">
        <div class="container mx-auto px-4 md:px-6">
            <div class="text-center mb-16 reveal">
                <h2 class="text-4xl md:text-5xl font-extrabold mb-4">Notre <span class="text-primary">Menu</span></h2>
                <div class="w-24 h-1 bg-primary mx-auto rounded-full"></div>
                <p class="text-gray-400 mt-4">Sélectionnez vos plats et commandez directement sur WhatsApp</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8" id="menu-grid">
                
                <!-- Helper to generate categories -->
                <script>
                    const menuData = [
                        {
                            title: "Plats Marocains",
                            image: "https://images.unsplash.com/photo-1541518763669-27fef04b14ea?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Salade Marocaine", price: 12 },
                                { name: "Viande Légumes", price: 30 },
                                { name: "Poulet Rôti", price: 35 },
                                { name: "لوبية", price: 15 },
                                { name: "كرعين", price: 40 },
                                { name: "دوارة", price: 35 }
                            ]
                        },
                        {
                            title: "Sandwich",
                            image: "https://images.unsplash.com/photo-1528735602780-2552fd46c7af?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Sandwich Dinde", price: 20 },
                                { name: "Sandwich Viande Hachée", price: 22 },
                                { name: "Sandwich Mixte", price: 25 },
                                { name: "Sandwich Thon", price: 18 }
                            ]
                        },
                        {
                            title: "Panini",
                            image: "https://images.unsplash.com/photo-1628840042765-356cda07504e?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Panini Poulet", price: 22 },
                                { name: "Panini Viande Hachée", price: 22 },
                                { name: "Panini Mixte", price: 25 },
                                { name: "Panini Thon", price: 18 }
                            ]
                        },
                        {
                            title: "Poutine",
                            image: "https://images.unsplash.com/photo-1586190848861-99aa4a171e90?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Poutine Dinde", price: 35 },
                                { name: "Poutine Viande Hachée", price: 38 },
                                { name: "Poutine Mixte", price: 40 }
                            ]
                        },
                        {
                            title: "Nugettes",
                            image: "https://images.unsplash.com/photo-1562967914-608f82629710?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "4 Pièces", price: 15 },
                                { name: "7 Pièces", price: 20 },
                                { name: "10 Pièces", price: 25 },
                                { name: "1 Muslitos Meal", price: 5 }
                            ]
                        },
                        {
                            title: "Tacos",
                            image: "https://images.unsplash.com/photo-1599974579688-8dbdd335c77f?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Tacos Dinde", price: 30 },
                                { name: "Tacos Viande Hachée", price: 32 },
                                { name: "Tacos Mixte", price: 32 },
                                { name: "Tacos Nuggets", price: 32 },
                                { name: "Tacos Cordon Bleu", price: 35 }
                            ]
                        },
                        {
                            title: "Tacos XL",
                            image: "https://images.unsplash.com/photo-1613655462372-911e86a048dc?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Tacos Dinde XL", price: 40 },
                                { name: "Tacos Viande Hachée XL", price: 42 },
                                { name: "Tacos Mixte XL", price: 44 },
                                { name: "Tacos Nuggets XL", price: 44 }
                            ]
                        },
                        {
                            title: "Burger",
                            image: "https://images.unsplash.com/photo-1568901346375-23c9450c58cd?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Hamburger", price: 22 },
                                { name: "Cheeseburger", price: 25 },
                                { name: "Big Burger", price: 32 },
                                { name: "Chicken Burger", price: 30 },
                                { name: "Double Chicken Burger", price: 40 },
                                { name: "Chicken Beef Burger", price: 40 },
                                { name: "Dynamite Burger", price: 45 }
                            ]
                        },
                        {
                            title: "Shawarma",
                            image: "https://images.unsplash.com/photo-1645367617277-241519d15024?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Shawarma", price: 25 },
                                { name: "Shawarma Extra", price: 30 }
                            ]
                        },
                        {
                            title: "Boissons",
                            image: "https://images.unsplash.com/photo-1622483767028-3f66f32aef97?auto=format&fit=crop&w=600&q=80",
                            items: [
                                { name: "Soda", price: 5 },
                                { name: "Eau 50cl", price: 5 }
                            ]
                        }
                    ];

                    const pizzas = {
                        title: "Les Pizzas",
                        image: "https://images.unsplash.com/photo-1513104890138-7c749659a591?auto=format&fit=crop&w=600&q=80",
                        items: [
                            { name: "Margarita", s: 18, m: 25 },
                            { name: "Thon", s: 22, m: 30 },
                            { name: "Poulet", s: 25, m: 30 },
                            { name: "Viande Hachée", s: 25, m: 30 },
                            { name: "Fruits de Mer", s: 30, m: 38 },
                            { name: "Végétarienne", s: 20, m: 28 },
                            { name: "Quatre Saisons", s: 30, m: 38 }
                        ]
                    };

                    function createQtyControl() {
                        return `
                            <div class="flex items-center bg-dark-lighter rounded-lg border border-gray-700 h-8">
                                <button type="button" class="w-8 h-full text-gray-400 hover:text-white hover:bg-gray-700 rounded-l-lg transition-colors qty-btn dec">-</button>
                                <input type="number" value="0" min="0" class="w-8 text-center bg-transparent text-white font-medium outline-none p-0 border-none text-sm pointer-events-none" readonly>
                                <button type="button" class="w-8 h-full text-gray-400 hover:text-white hover:bg-gray-700 rounded-r-lg transition-colors qty-btn inc">+</button>
                            </div>
                        `;
                    }

                    const menuGrid = document.getElementById('menu-grid');

                    // Render Standard Categories
                    menuData.forEach((cat, index) => {
                        let itemsHtml = cat.items.map(item => `
                            <div class="menu-item flex justify-between items-center py-3 border-b border-gray-800 last:border-0">
                                <h4 class="text-gray-200 font-medium item-name pr-2">${item.name}</h4>
                                <div class="flex items-center gap-3 shrink-0">
                                    <span class="text-primary font-bold item-price" data-price="${item.price}">${item.price} DH</span>
                                    ${createQtyControl()}
                                </div>
                            </div>
                        `).join('');

                        menuGrid.innerHTML += `
                            <div class="menu-category bg-dark-card rounded-2xl shadow-xl overflow-hidden border border-gray-800 hover:border-gray-700 transition-all reveal" style="transition-delay: ${index * 50}ms">
                                <div class="h-48 relative overflow-hidden group">
                                    <img src="${cat.image}" alt="${cat.title}" class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-500">
                                    <div class="absolute inset-0 bg-gradient-to-t from-dark-card to-transparent"></div>
                                </div>
                                <div class="bg-primary text-white text-center py-3 font-bold text-xl uppercase tracking-wider shadow-md relative z-10">
                                    ${cat.title}
                                </div>
                                <div class="p-5">
                                    <div class="flex flex-col mb-4">
                                        ${itemsHtml}
                                    </div>
                                    <button class="w-full py-3 mt-2 bg-dark-lighter border border-primary/50 text-primary font-bold rounded-xl hover:bg-primary hover:text-white transition-all order-cat-btn flex items-center justify-center gap-2">
                                        <i class="fa-brands fa-whatsapp text-lg"></i> Commander
                                    </button>
                                </div>
                            </div>
                        `;
                    });

                    // Render Pizza Category (Special Layout)
                    let pizzaItemsHtml = pizzas.items.map(item => `
                        <div class="menu-item flex flex-col py-3 border-b border-gray-800 last:border-0">
                            <h4 class="text-gray-200 font-medium item-name mb-2">${item.name}</h4>
                            
                            <div class="flex justify-between items-center pl-4 mb-2 sub-item">
                                <span class="text-sm text-gray-400 size-name">Taille S</span>
                                <div class="flex items-center gap-3 shrink-0">
                                    <span class="text-primary font-bold item-price" data-price="${item.s}">${item.s} DH</span>
                                    ${createQtyControl()}
                                </div>
                            </div>
                            
                            <div class="flex justify-between items-center pl-4 sub-item">
                                <span class="text-sm text-gray-400 size-name">Taille M</span>
                                <div class="flex items-center gap-3 shrink-0">
                                    <span class="text-primary font-bold item-price" data-price="${item.m}">${item.m} DH</span>
                                    ${createQtyControl()}
                                </div>
                            </div>
                        </div>
                    `).join('');

                    menuGrid.innerHTML += `
                        <div class="menu-category bg-dark-card rounded-2xl shadow-xl overflow-hidden border border-gray-800 hover:border-gray-700 transition-all reveal md:col-span-2 lg:col-span-1">
                            <div class="h-48 relative overflow-hidden group">
                                <img src="${pizzas.image}" alt="${pizzas.title}" class="w-full h-full object-cover transform group-hover:scale-110 transition-transform duration-500">
                                <div class="absolute inset-0 bg-gradient-to-t from-dark-card to-transparent"></div>
                            </div>
                            <div class="bg-primary text-white text-center py-3 font-bold text-xl uppercase tracking-wider shadow-md relative z-10 flex flex-col">
                                <span>${pizzas.title}</span>
                                <span class="text-xs font-normal bg-black/20 px-2 py-0.5 rounded mx-auto mt-1">S | M</span>
                            </div>
                            <div class="p-5">
                                <div class="flex flex-col mb-4">
                                    ${pizzaItemsHtml}
                                </div>
                                <button class="w-full py-3 mt-2 bg-dark-lighter border border-primary/50 text-primary font-bold rounded-xl hover:bg-primary hover:text-white transition-all order-cat-btn flex items-center justify-center gap-2">
                                    <i class="fa-brands fa-whatsapp text-lg"></i> Commander
                                </button>
                            </div>
                        </div>
                    `;
                </script>
            </div>
        </div>
    </section>

    <!-- Location Section -->
    <section id="localisation" class="py-24 bg-dark border-t border-gray-800">
        <div class="container mx-auto px-6">
            <div class="text-center mb-12 reveal">
                <h2 class="text-3xl md:text-4xl font-bold mb-4">Notre <span class="text-primary">Localisation</span></h2>
                <p class="text-gray-400">Venez nous rendre visite à Oujda !</p>
            </div>

            <div class="max-w-4xl mx-auto reveal delay-100">
                <div class="bg-dark-card p-2 rounded-3xl border border-gray-800 shadow-2xl mb-6 relative overflow-hidden">
                    <!-- Generic map embed for Oujda, as the exact link is a shortlink and cannot be iframed directly -->
                    <iframe 
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d105073.44367000781!2d-1.9567946894042852!3d34.681395804365774!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0xd7864985db586c9%3A0xc3f5d5cc70fbf1a8!2sOujda%2C%20Morocco!5e0!3m2!1sen!2sus!4v1700000000000!5m2!1sen!2sus" 
                        width="100%" 
                        height="400" 
                        style="border:0; border-radius: 1.25rem; filter: invert(90%) hue-rotate(180deg);" 
                        allowfullscreen="" 
                        loading="lazy" 
                        referrerpolicy="no-referrer-when-downgrade">
                    </iframe>
                </div>
                
                <div class="flex flex-col sm:flex-row items-center justify-between bg-dark-lighter p-6 rounded-2xl border border-gray-800">
                    <div class="flex items-center gap-4 mb-4 sm:mb-0">
                        <div class="w-12 h-12 bg-primary/20 text-primary rounded-full flex items-center justify-center text-xl">
                            <i class="fa-solid fa-location-dot"></i>
                        </div>
                        <div>
                            <h4 class="font-bold text-lg">City Meal</h4>
                            <p class="text-gray-400 text-sm">Oujda, Maroc</p>
                        </div>
                    </div>
                    <a href="https://maps.app.goo.gl/PcSym2AWGB7ZuU347" target="_blank" class="px-6 py-3 bg-white text-black font-bold rounded-xl hover:bg-gray-200 transition-colors flex items-center gap-2 w-full sm:w-auto justify-center">
                        <i class="fa-solid fa-map"></i> Ouvrir dans Google Maps
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer / Contact -->
    <footer id="contact" class="bg-[#050505] pt-16 pb-8 border-t border-gray-900">
        <div class="container mx-auto px-6">
            <div class="grid grid-cols-1 md:grid-cols-3 gap-12 mb-12">
                <!-- Brand -->
                <div>
                    <a href="#" class="text-3xl font-bold tracking-tighter flex items-center gap-2 mb-6">
                        <i class="fa-solid fa-utensils text-primary"></i>
                        <span class="text-white">City</span><span class="text-primary">Meal</span>
                    </a>
                    <p class="text-gray-400 mb-6 text-sm leading-relaxed">
                        L'adresse incontournable à Oujda pour des plats marocains authentiques et des fast foods de qualité premium.
                    </p>
                    <div class="flex gap-4">
                        <a href="https://www.instagram.com/city_meal_oujda?igsh=YmdjdjJiZDZwZnhp" target="_blank" class="w-10 h-10 rounded-full bg-dark-lighter flex items-center justify-center text-white hover:bg-gradient-to-tr hover:from-yellow-400 hover:via-red-500 hover:to-purple-500 transition-all transform hover:-translate-y-1">
                            <i class="fa-brands fa-instagram text-lg"></i>
                        </a>
                        <a href="https://wa.me/212616970672" target="_blank" class="w-10 h-10 rounded-full bg-dark-lighter flex items-center justify-center text-white hover:bg-[#25D366] transition-all transform hover:-translate-y-1">
                            <i class="fa-brands fa-whatsapp text-lg"></i>
                        </a>
                    </div>
                </div>

                <!-- Contact Info -->
                <div>
                    <h4 class="text-xl font-bold mb-6 text-white border-b border-gray-800 pb-2 inline-block">Contactez-nous</h4>
                    <ul class="space-y-4">
                        <li class="flex items-center gap-3 text-gray-400 hover:text-white transition-colors">
                            <i class="fa-solid fa-phone text-primary w-5 text-center"></i>
                            <a href="tel:0616970672" class="font-medium text-lg tracking-wider">0616970672</a>
                        </li>
                        <li class="flex items-center gap-3 text-gray-400">
                            <i class="fa-brands fa-whatsapp text-primary w-5 text-center"></i>
                            <a href="https://wa.me/212616970672" target="_blank" class="hover:text-[#25D366] transition-colors">Commander via WhatsApp</a>
                        </li>
                        <li class="flex flex-start gap-3 text-gray-400">
                            <i class="fa-solid fa-location-dot text-primary w-5 text-center mt-1"></i>
                            <span>Oujda, Maroc</span>
                        </li>
                    </ul>
                </div>

                <!-- Hours -->
                <div>
                    <h4 class="text-xl font-bold mb-6 text-white border-b border-gray-800 pb-2 inline-block">Heures d'ouverture</h4>
                    <div class="bg-dark-card p-4 rounded-xl border border-gray-800 flex items-center gap-4">
                        <i class="fa-regular fa-clock text-3xl text-primary"></i>
                        <div>
                            <p class="text-white font-medium">Tous les jours</p>
                            <p class="text-primary font-bold text-xl">11:00 – 23:30</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="text-center border-t border-gray-800 pt-8 text-gray-500 text-sm flex flex-col md:flex-row justify-between items-center gap-4">
                <p>&copy; <span id="year"></span> City Meal. Tous droits réservés.</p>
                <button id="back-to-top" class="w-10 h-10 bg-dark-lighter text-primary rounded-full hover:bg-primary hover:text-white transition-colors flex items-center justify-center focus:outline-none">
                    <i class="fa-solid fa-arrow-up"></i>
                </button>
            </div>
        </div>
    </footer>

    <!-- Global Order Action (Optional enhancement, hidden by default but logic exists) -->
    <!-- Scripts -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            // Set current year
            document.getElementById('year').textContent = new Date().getFullYear();

            // Mobile Menu Toggle
            const btn = document.getElementById('mobile-menu-btn');
            const menu = document.getElementById('mobile-menu');
            const mobileLinks = document.querySelectorAll('.mobile-link');
            const icon = btn.querySelector('i');

            function toggleMenu() {
                menu.classList.toggle('hidden');
                menu.classList.toggle('flex');
                if(menu.classList.contains('hidden')) {
                    icon.classList.remove('fa-xmark');
                    icon.classList.add('fa-bars');
                } else {
                    icon.classList.remove('fa-bars');
                    icon.classList.add('fa-xmark');
                }
            }

            btn.addEventListener('click', toggleMenu);
            mobileLinks.forEach(link => link.addEventListener('click', toggleMenu));

            // Sticky Navbar
            const navbar = document.getElementById('navbar');
            window.addEventListener('scroll', () => {
                if (window.scrollY > 50) {
                    navbar.classList.add('scrolled');
                } else {
                    navbar.classList.remove('scrolled');
                }
            });

            // Back to top
            const backToTop = document.getElementById('back-to-top');
            backToTop.addEventListener('click', () => {
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });

            // Scroll Reveal
            const reveals = document.querySelectorAll('.reveal');
            const revealOptions = {
                threshold: 0.1,
                rootMargin: "0px 0px -50px 0px"
            };

            const revealOnScroll = new IntersectionObserver(function(entries, observer) {
                entries.forEach(entry => {
                    if (!entry.isIntersecting) return;
                    entry.target.classList.add('active');
                    observer.unobserve(entry.target);
                });
            }, revealOptions);

            reveals.forEach(reveal => {
                revealOnScroll.observe(reveal);
            });

            // Quantity Control Logic
            document.addEventListener('click', (e) => {
                if(e.target.classList.contains('qty-btn')) {
                    const isInc = e.target.classList.contains('inc');
                    const input = e.target.parentElement.querySelector('input');
                    let val = parseInt(input.value) || 0;
                    
                    if (isInc) {
                        val++;
                    } else if (val > 0) {
                        val--;
                    }
                    
                    input.value = val;
                    
                    // Highlight input if > 0
                    if(val > 0) {
                        input.classList.add('text-primary');
                        input.classList.remove('text-white');
                    } else {
                        input.classList.remove('text-primary');
                        input.classList.add('text-white');
                    }
                }
            });

            // Order per category Logic
            const phone = "212616970672";
            
            document.querySelectorAll('.order-cat-btn').forEach(btn => {
                btn.addEventListener('click', (e) => {
                    const categoryCard = e.target.closest('.menu-category');
                    const catTitle = categoryCard.querySelector('.bg-primary').innerText.trim();
                    const items = categoryCard.querySelectorAll('.menu-item');
                    
                    let orderDetails = [];
                    let total = 0;

                    items.forEach(item => {
                        // Check if it's a simple item or has sub-items (like Pizza)
                        const subItems = item.querySelectorAll('.sub-item');
                        
                        if(subItems.length > 0) {
                            // Handle Pizza sizes
                            const baseName = item.querySelector('.item-name').innerText;
                            subItems.forEach(sub => {
                                const input = sub.querySelector('input');
                                const val = parseInt(input.value) || 0;
                                if(val > 0) {
                                    const size = sub.querySelector('.size-name').innerText.replace('Taille ', '');
                                    const price = parseInt(sub.querySelector('.item-price').dataset.price);
                                    orderDetails.push(`- ${val}x ${baseName} (${size}) : ${price * val} DH`);
                                    total += price * val;
                                }
                            });
                        } else {
                            // Handle normal items
                            const input = item.querySelector('input');
                            if(input) {
                                const val = parseInt(input.value) || 0;
                                if(val > 0) {
                                    const name = item.querySelector('.item-name').innerText;
                                    const price = parseInt(item.querySelector('.item-price').dataset.price);
                                    orderDetails.push(`- ${val}x ${name} : ${price * val} DH`);
                                    total += price * val;
                                }
                            }
                        }
                    });

                    if(orderDetails.length > 0) {
                        const intro = `Bonjour City Meal, je veux commander depuis la catégorie *${catTitle}* :`;
                        const textMsg = `${intro}\n\n${orderDetails.join('\n')}\n\n*Total : ${total} DH*`;
                        const url = `https://wa.me/${phone}?text=${encodeURIComponent(textMsg)}`;
                        window.open(url, '_blank');
                    } else {
                        // Soft alert using a visual cue
                        const originalText = btn.innerHTML;
                        btn.innerHTML = `<i class="fa-solid fa-circle-exclamation"></i> Sélectionnez un article`;
                        btn.classList.replace('text-primary', 'text-red-500');
                        btn.classList.replace('border-primary/50', 'border-red-500/50');
                        setTimeout(() => {
                            btn.innerHTML = originalText;
                            btn.classList.replace('text-red-500', 'text-primary');
                            btn.classList.replace('border-red-500/50', 'border-primary/50');
                        }, 2000);
                    }
                });
            });
        });

        // Global Hero Button Order (Just opens WA with pre-filled intro as requested)
        function orderNowGlobal() {
            const phone = "212616970672";
            const textMsg = "Bonjour City Meal, je veux commander :";
            const url = `https://wa.me/${phone}?text=${encodeURIComponent(textMsg)}`;
            window.open(url, '_blank');
        }
    </script>
</body>
</html>
```
