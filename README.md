# PROYECTO-WEB-FUNDAMENTOS-INGENIERIA-EN-SOFTWARE-22380314
Proyeto web para un restaurant 
ALUMNO: GEAN FRANCISCO ORTIZ ROBLES 22380314
LINK DE WEB https://webrestaurant.my.canva.site/
CODIGO:
<!doctype html>
<html lang="es">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>El Rincón de las Alitas - Restaurante</title>
  <script src="/_sdk/data_sdk.js"></script>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      box-sizing: border-box;
    }
    
    * {
      box-sizing: border-box;
    }
    
    .custom-section {
      scroll-margin-top: 80px;
    }
    
    .menu-item-card {
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      backdrop-filter: blur(10px);
    }
    
    .menu-item-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 8px 16px rgba(255, 107, 53, 0.3);
    }
    
    .nav-link {
      transition: color 0.2s ease;
    }
    
    .loading-spinner {
      border: 3px solid rgba(255,255,255,0.3);
      border-radius: 50%;
      border-top: 3px solid white;
      width: 20px;
      height: 20px;
      animation: spin 1s linear infinite;
    }
    
    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }
    
    .hero-pattern {
      background-image: 
        radial-gradient(circle at 20% 50%, rgba(255, 107, 53, 0.15) 0%, transparent 50%),
        radial-gradient(circle at 80% 80%, rgba(247, 147, 30, 0.15) 0%, transparent 50%),
        radial-gradient(circle at 40% 20%, rgba(255, 107, 53, 0.1) 0%, transparent 50%);
    }
    
    .animated-gradient {
      background: linear-gradient(135deg, rgba(20, 20, 20, 0.95) 0%, rgba(40, 20, 10, 0.95) 50%, rgba(20, 20, 20, 0.95) 100%);
      background-size: 200% 200%;
      animation: gradientShift 15s ease infinite;
    }
    
    @keyframes gradientShift {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }
    
    .pattern-dots {
      background-image: 
        radial-gradient(circle at 10% 20%, rgba(255, 107, 53, 0.15) 0%, transparent 50%),
        radial-gradient(circle at 90% 80%, rgba(247, 147, 30, 0.15) 0%, transparent 50%),
        radial-gradient(circle, rgba(255, 107, 53, 0.08) 1px, transparent 1px);
      background-size: 800px 800px, 800px 800px, 40px 40px;
    }
    
    .glass-effect {
      backdrop-filter: blur(10px);
      border: 1px solid rgba(255, 107, 53, 0.2);
    }
  </style>
  <style>@view-transition { navigation: auto; }</style>
 </head>
 <body class="w-full min-h-full animated-gradient pattern-dots"><!-- Toggle Modo Claro/Oscuro --> <button id="theme-toggle" class="fixed top-4 left-4 z-50 p-3 rounded-full shadow-lg transition-all hover:scale-110">
   <svg id="sun-icon" class="w-6 h-6 hidden" fill="currentColor" viewbox="0 0 20 20"><path fill-rule="evenodd" d="M10 2a1 1 0 011 1v1a1 1 0 11-2 0V3a1 1 0 011-1zm4 8a4 4 0 11-8 0 4 4 0 018 0zm-.464 4.95l.707.707a1 1 0 001.414-1.414l-.707-.707a1 1 0 00-1.414 1.414zm2.12-10.607a1 1 0 010 1.414l-.706.707a1 1 0 11-1.414-1.414l.707-.707a1 1 0 011.414 0zM17 11a1 1 0 100-2h-1a1 1 0 100 2h1zm-7 4a1 1 0 011 1v1a1 1 0 11-2 0v-1a1 1 0 011-1zM5.05 6.464A1 1 0 106.465 5.05l-.708-.707a1 1 0 00-1.414 1.414l.707.707zm1.414 8.486l-.707.707a1 1 0 01-1.414-1.414l.707-.707a1 1 0 011.414 1.414zM4 11a1 1 0 100-2H3a1 1 0 000 2h1z" clip-rule="evenodd" />
   </svg>
   <svg id="moon-icon" class="w-6 h-6" fill="currentColor" viewbox="0 0 20 20"><path d="M17.293 13.293A8 8 0 016.707 2.707a8.001 8.001 0 1010.586 10.586z" />
   </svg></button> <!-- Navegación -->
  <nav id="navbar" class="w-full fixed top-0 left-0 z-50 shadow-md">
   <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center h-20">
     <div class="flex-shrink-0">
      <h1 id="nav-title" class="text-2xl font-bold">El Rincón de las Alitas</h1>
     </div>
     <div class="hidden md:block">
      <div class="flex space-x-6"><a href="#inicio" class="nav-link font-medium">Inicio</a> <a href="#menu" class="nav-link font-medium">Menú</a> <a href="#reservaciones" class="nav-link font-medium">Reservaciones</a> <a href="#domicilio" class="nav-link font-medium">Domicilio</a> <a href="#contacto" class="nav-link font-medium">Contacto</a> <a href="#resenas" class="nav-link font-medium">Reseñas</a>
      </div>
     </div>
    </div>
   </div>
  </nav><!-- Hero Section -->
  <section id="inicio" class="w-full pt-20 custom-section hero-pattern">
   <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 text-center relative"><!-- Decorative SVG Images -->
    <div class="absolute top-10 left-10 opacity-20 hidden lg:block">
     <svg width="120" height="120" viewbox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg"><circle cx="60" cy="60" r="50" fill="#ff6b35" /> <circle cx="60" cy="55" r="35" fill="#f7931e" /> <rect x="40" y="75" width="40" height="8" rx="4" fill="#ff6b35" /> <circle cx="50" cy="50" r="3" fill="#fff" /> <circle cx="70" cy="50" r="3" fill="#fff" /> <path d="M45 65 Q60 75 75 65" stroke="#fff" stroke-width="2" fill="none" />
     </svg>
    </div>
    <div class="absolute top-20 right-10 opacity-20 hidden lg:block">
     <svg width="100" height="100" viewbox="0 0 100 100" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M50 10 L60 35 L85 35 L65 50 L75 75 L50 60 L25 75 L35 50 L15 35 L40 35 Z" fill="#f7931e" /> <circle cx="50" cy="45" r="15" fill="#ff6b35" />
     </svg>
    </div>
    <h2 id="hero-title" class="text-5xl font-bold mb-4">El Rincón de las Alitas</h2>
    <p id="hero-tagline" class="text-xl mb-8">Las mejores hamburguesas y alitas de la ciudad</p>
    <div class="flex justify-center gap-4"><a href="#menu" class="btn-primary px-8 py-3 rounded-lg font-semibold shadow-lg transition-all hover:shadow-xl">Ver Menú</a> <a href="#reservaciones" class="btn-secondary px-8 py-3 rounded-lg font-semibold shadow-lg transition-all hover:shadow-xl">Reservar Mesa</a>
    </div>
   </div>
  </section><!-- Menú -->
  <section id="menu" class="w-full py-16 custom-section">
   <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <h2 id="menu-title" class="text-4xl font-bold text-center mb-12">Nuestro Menú</h2><!-- Entradas -->
    <div class="mb-12">
     <h3 class="text-3xl font-bold mb-6">Entradas</h3>
     <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1639024471283-03518883512d?w=800&amp;q=80" alt="Aros de Cebolla" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Aros de Cebolla</h4>
        <p class="mb-3">Crujientes aros de cebolla dorados con salsa ranch</p>
        <p class="text-2xl font-bold">$125 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1513456852971-30c0b8199d4d?w=800&amp;q=80" alt="Nachos Supremos" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Nachos Supremos</h4>
        <p class="mb-3">Nachos con queso, jalapeños, guacamole y crema</p>
        <p class="text-2xl font-bold">$160 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1631452180519-c014fe946bc7?w=800&amp;q=80" alt="Dedos de Queso" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Dedos de Queso</h4>
        <p class="mb-3">Palitos de queso mozzarella empanizados</p>
        <p class="text-2xl font-bold">$135 MXN</p>
       </div>
      </div>
     </div>
    </div><!-- Platos Fuertes -->
    <div class="mb-12">
     <h3 class="text-3xl font-bold mb-6">Platos Fuertes</h3>
     <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1568901346375-23c9450c58cd?w=800&amp;q=80" alt="Hamburguesa Clásica" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Hamburguesa Clásica</h4>
        <p class="mb-3">Carne de res, lechuga, tomate, cebolla y queso</p>
        <p class="text-2xl font-bold">$230 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1550547660-d9450f859349?w=800&amp;q=80" alt="Hamburguesa BBQ Bacon" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Hamburguesa BBQ Bacon</h4>
        <p class="mb-3">Carne, tocino, queso cheddar, cebolla caramelizada y salsa BBQ</p>
        <p class="text-2xl font-bold">$285 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1608039755401-742074f0548d?w=800&amp;q=80" alt="Alitas Búfalo" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Alitas Búfalo (12 piezas)</h4>
        <p class="mb-3">Alitas picantes con salsa búfalo y aderezo ranch</p>
        <p class="text-2xl font-bold">$270 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1527477396000-e27163b481c2?w=800&amp;q=80" alt="Alitas BBQ" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Alitas BBQ (12 piezas)</h4>
        <p class="mb-3">Alitas glaseadas con nuestra salsa BBQ especial</p>
        <p class="text-2xl font-bold">$270 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1562967914-608f82629710?w=800&amp;q=80" alt="Combo Wings &amp; Burger" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Combo Wings &amp; Burger</h4>
        <p class="mb-3">1 hamburguesa + 6 alitas + papas fritas</p>
        <p class="text-2xl font-bold">$420 MXN</p>
       </div>
      </div>
     </div>
    </div><!-- Postres -->
    <div class="mb-12">
     <h3 class="text-3xl font-bold mb-6">Postres</h3>
     <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1564355808539-22fda35bed7e?w=800&amp;q=80" alt="Brownie con Helado" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Brownie con Helado</h4>
        <p class="mb-3">Brownie de chocolate caliente con helado de vainilla</p>
        <p class="text-2xl font-bold">$125 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1533134486753-c833f0ed4866?w=800&amp;q=80" alt="Cheesecake" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Cheesecake</h4>
        <p class="mb-3">Pastel de queso cremoso con salsa de frutos rojos</p>
        <p class="text-2xl font-bold">$135 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1563805042-7684c019e1cb?w=800&amp;q=80" alt="Sundae de Chocolate" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Sundae de Chocolate</h4>
        <p class="mb-3">Helado con salsa de chocolate, crema y cereza</p>
        <p class="text-2xl font-bold">$110 MXN</p>
       </div>
      </div>
     </div>
    </div><!-- Bebidas -->
    <div class="mb-12">
     <h3 class="text-3xl font-bold mb-6">Bebidas</h3>
     <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1581006852262-e4307cf6283a?w=800&amp;q=80" alt="Refrescos" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Refrescos</h4>
        <p class="mb-3">Coca-Cola, Sprite, Fanta</p>
        <p class="text-2xl font-bold">$50 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1523677011781-c91d1bbe2f8d?w=800&amp;q=80" alt="Limonada Natural" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Limonada Natural</h4>
        <p class="mb-3">Limonada fresca hecha en casa</p>
        <p class="text-2xl font-bold">$60 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1572490122747-3968b75cc699?w=800&amp;q=80" alt="Milkshake" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Milkshake</h4>
        <p class="mb-3">Chocolate, vainilla o fresa</p>
        <p class="text-2xl font-bold">$110 MXN</p>
       </div>
      </div>
      <div class="menu-item-card rounded-lg shadow-md overflow-hidden">
       <div class="relative h-48 overflow-hidden"><img src="https://images.unsplash.com/photo-1608270586620-248524c67de9?w=800&amp;q=80" alt="Cerveza" class="w-full h-full object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 to-transparent"></div>
       </div>
       <div class="p-6">
        <h4 class="text-xl font-bold mb-2">Cerveza</h4>
        <p class="mb-3">Variedad de cervezas nacionales</p>
        <p class="text-2xl font-bold">$90 MXN</p>
       </div>
      </div>
     </div>
    </div>
   </div>
  </section><!-- Reservaciones -->
  <section id="reservaciones" class="w-full py-16 custom-section">
   <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-4xl font-bold text-center mb-12">Reservaciones</h2>
    <div class="reservation-form-card glass-effect p-8 rounded-lg shadow-lg">
     <form id="reservation-form">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
       <div><label for="res-name" class="block text-sm font-semibold mb-2">Nombre Completo</label> <input type="text" id="res-name" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2">
       </div>
       <div><label for="res-email" class="block text-sm font-semibold mb-2">Email</label> <input type="email" id="res-email" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2">
       </div>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
       <div><label for="res-phone" class="block text-sm font-semibold mb-2">Teléfono</label> <input type="tel" id="res-phone" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2">
       </div>
       <div><label for="res-guests" class="block text-sm font-semibold mb-2">Número de Personas</label> <input type="number" id="res-guests" min="1" max="20" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2">
       </div>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
       <div><label for="res-date" class="block text-sm font-semibold mb-2">Fecha</label> <input type="date" id="res-date" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2">
       </div>
       <div><label for="res-time" class="block text-sm font-semibold mb-2">Hora</label> <select id="res-time" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2"> <option value="">Seleccionar hora</option> <option value="12:00">12:00 PM</option> <option value="12:30">12:30 PM</option> <option value="13:00">1:00 PM</option> <option value="13:30">1:30 PM</option> <option value="14:00">2:00 PM</option> <option value="14:30">2:30 PM</option> <option value="18:00">6:00 PM</option> <option value="18:30">6:30 PM</option> <option value="19:00">7:00 PM</option> <option value="19:30">7:30 PM</option> <option value="20:00">8:00 PM</option> <option value="20:30">8:30 PM</option> <option value="21:00">9:00 PM</option> </select>
       </div>
      </div><button type="submit" id="res-submit-btn" class="w-full btn-primary py-3 rounded-lg font-semibold text-lg shadow-lg transition-all hover:shadow-xl flex items-center justify-center"> <span id="res-submit-text">Reservar Ahora</span> </button>
     </form>
     <div id="res-success-message" class="mt-6 p-4 rounded-lg hidden">
      <p class="font-semibold text-center">¡Reservación confirmada! Te enviaremos un email de confirmación.</p>
     </div>
    </div>
   </div>
  </section><!-- Servicio a Domicilio -->
  <section id="domicilio" class="w-full py-16 custom-section">
   <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-4xl font-bold text-center mb-12">Servicio a Domicilio</h2>
    <div class="delivery-card glass-effect p-8 rounded-lg shadow-lg text-center">
     <h3 class="text-2xl font-bold mb-4">Pedidos a Domicilio</h3>
     <p class="text-lg mb-8">Llevamos nuestras deliciosas hamburguesas y alitas directo a tu puerta</p>
     <div class="grid grid-cols-1 md:grid-cols-3 gap-8 mb-8">
      <div class="glass-effect p-6 rounded-lg">
       <div class="mb-4 flex justify-center"><img src="https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=400&amp;q=80" alt="Entrega Rápida" class="w-24 h-24 object-cover rounded-full border-4 border-orange-500">
       </div>
       <p class="font-bold text-xl mb-2">30-45 minutos</p>
       <p class="text-sm opacity-80">Tiempo de entrega promedio</p>
      </div>
      <div class="glass-effect p-6 rounded-lg relative overflow-hidden">
       <div class="absolute top-2 right-2 bg-green-500 text-white px-3 py-1 rounded-full text-xs font-bold transform rotate-12">
        ¡GRATIS!
       </div>
       <div class="mb-4 flex justify-center"><img src="https://images.unsplash.com/photo-1607863680198-23d4b2565df0?w=400&amp;q=80" alt="Envío Gratis" class="w-24 h-24 object-cover rounded-full border-4 border-green-500">
       </div>
       <p class="font-bold text-xl mb-2">Envío $50 MXN</p>
       <p class="text-sm opacity-80">Gratis en pedidos mayores a $500</p>
      </div>
      <div class="glass-effect p-6 rounded-lg">
       <div class="mb-4 flex justify-center"><img src="https://images.unsplash.com/photo-1524661135-423995f22d0b?w=400&amp;q=80" alt="Área de Cobertura" class="w-24 h-24 object-cover rounded-full border-4 border-blue-500">
       </div>
       <p class="font-bold text-xl mb-2">5km de radio</p>
       <p class="text-sm opacity-80">Área de cobertura (Satélite)</p>
      </div>
     </div>
     <div class="space-y-3">
      <p id="delivery-phone" class="text-xl font-bold">Llama al: +1 (555) 123-4567</p>
      <p class="text-lg">Horario: Lunes a Domingo 11:00 AM - 11:00 PM</p>
     </div>
    </div>
   </div>
  </section><!-- Contacto / Atención al Cliente -->
  <section id="contacto" class="w-full py-16 custom-section">
   <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-4xl font-bold text-center mb-12">Atención al Cliente</h2>
    <div class="contact-form-card glass-effect p-8 rounded-lg shadow-lg">
     <form id="contact-form">
      <div class="mb-6"><label for="contact-name" class="block text-sm font-semibold mb-2">Nombre</label> <input type="text" id="contact-name" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2">
      </div>
      <div class="mb-6"><label for="contact-email" class="block text-sm font-semibold mb-2">Email</label> <input type="email" id="contact-email" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2">
      </div>
      <div class="mb-6"><label for="contact-message" class="block text-sm font-semibold mb-2">Mensaje / Sugerencia</label> <textarea id="contact-message" rows="5" required class="w-full px-4 py-2 rounded-lg border-2 focus:outline-none focus:ring-2"></textarea>
      </div><button type="submit" id="contact-submit-btn" class="w-full btn-primary py-3 rounded-lg font-semibold text-lg shadow-lg transition-all hover:shadow-xl flex items-center justify-center"> <span id="contact-submit-text">Enviar Mensaje</span> </button>
     </form>
     <div id="contact-success-message" class="mt-6 p-4 rounded-lg hidden">
      <p class="font-semibold text-center">¡Mensaje enviado! Te responderemos pronto.</p>
     </div>
    </div>
   </div>
  </section><!-- Reseñas -->
  <section id="resenas" class="w-full py-16 custom-section">
   <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8">
    <h2 class="text-4xl font-bold text-center mb-12">Lo Que Dicen Nuestros Clientes</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
     <div class="review-card glass-effect p-6 rounded-lg shadow-lg">
      <div class="flex items-center mb-4">
       <div>
        <h4 class="font-bold">Carlos Rodríguez</h4>
        <div class="text-yellow-400">
         ★★★★★
        </div>
       </div>
      </div>
      <p class="italic">"Las mejores alitas que he probado en mi vida. La salsa búfalo es perfecta, el lugar es acogedor y el servicio excepcional. ¡Totalmente recomendado!"</p>
     </div>
     <div class="review-card glass-effect p-6 rounded-lg shadow-lg">
      <div class="flex items-center mb-4">
       <div>
        <h4 class="font-bold">María González</h4>
        <div class="text-yellow-400">
         ★★★★★
        </div>
       </div>
      </div>
      <p class="italic">"La hamburguesa BBQ Bacon es increíble. Jugosa, bien sazonada y con ingredientes frescos. El servicio a domicilio siempre llega caliente y puntual."</p>
     </div>
     <div class="review-card glass-effect p-6 rounded-lg shadow-lg">
      <div class="flex items-center mb-4">
       <div>
        <h4 class="font-bold">Familia Martínez</h4>
        <div class="text-yellow-400">
         ★★★★★
        </div>
       </div>
      </div>
      <p class="italic">"Nuestro lugar favorito para comer en familia. Los niños aman las hamburguesas y nosotros las alitas. Excelente relación calidad-precio."</p>
     </div>
    </div>
   </div>
  </section><!-- Footer -->
  <footer class="w-full py-8">
   <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
    <div class="mb-4">
     <p class="text-lg font-semibold mb-2">Síguenos en Redes Sociales</p>
     <div class="flex justify-center gap-6 text-lg"><span>Facebook</span> <span>Instagram</span> <span>Twitter</span>
     </div>
    </div>
    <p id="footer-text" class="text-sm">© 2024 El Rincón de las Alitas. Todos los derechos reservados.</p>
   </div>
  </footer>
  <script>
    const defaultConfig = {
      background_color: "#1a1a1a",
      surface_color: "#2d2d2d",
      text_color: "#ffffff",
      primary_action_color: "#ff6b35",
      secondary_action_color: "#f7931e",
      font_family: "system-ui",
      font_size: 16,
      restaurant_name: "El Rincón de las Alitas",
      tagline: "Las mejores hamburguesas y alitas de la ciudad",
      menu_title: "Nuestro Menú",
      contact_phone: "+1 (555) 123-4567",
      contact_email: "info@wingsandburgers.com",
      footer_text: "© 2024 El Rincón de las Alitas. Todos los derechos reservados."
    };

    const lightTheme = {
      background: "#f5f5f5",
      surface: "#ffffff",
      text: "#1a1a1a",
      primary: "#ff6b35",
      secondary: "#f7931e"
    };

    const darkTheme = {
      background: "#1a1a1a",
      surface: "#2d2d2d",
      text: "#ffffff",
      primary: "#ff6b35",
      secondary: "#f7931e"
    };

    let currentData = [];
    let recordCount = 0;
    let isDarkMode = true;

    const dataHandler = {
      onDataChanged(data) {
        currentData = data;
        recordCount = data.length;
      }
    };

    async function onConfigChange(config) {
      const customFont = config.font_family || defaultConfig.font_family;
      const baseSize = config.font_size || defaultConfig.font_size;
      const baseFontStack = 'Arial, sans-serif';
      const fontFamily = `${customFont}, ${baseFontStack}`;

      document.body.style.backgroundColor = config.background_color || defaultConfig.background_color;
      document.body.style.color = config.text_color || defaultConfig.text_color;
      document.body.style.fontFamily = fontFamily;
      document.body.style.fontSize = `${baseSize}px`;

      const navbar = document.getElementById('navbar');
      navbar.style.backgroundColor = config.surface_color || defaultConfig.surface_color;

      const navTitle = document.getElementById('nav-title');
      navTitle.textContent = config.restaurant_name || defaultConfig.restaurant_name;
      navTitle.style.color = config.text_color || defaultConfig.text_color;
      navTitle.style.fontFamily = fontFamily;
      navTitle.style.fontSize = `${baseSize * 1.5}px`;

      const navLinks = document.querySelectorAll('.nav-link');
      navLinks.forEach(link => {
        link.style.color = config.text_color || defaultConfig.text_color;
        link.style.fontFamily = fontFamily;
        link.style.fontSize = `${baseSize}px`;
        link.addEventListener('mouseenter', function() {
          this.style.color = config.primary_action_color || defaultConfig.primary_action_color;
        });
        link.addEventListener('mouseleave', function() {
          this.style.color = config.text_color || defaultConfig.text_color;
        });
      });

      const heroTitle = document.getElementById('hero-title');
      heroTitle.textContent = config.restaurant_name || defaultConfig.restaurant_name;
      heroTitle.style.color = config.text_color || defaultConfig.text_color;
      heroTitle.style.fontFamily = fontFamily;
      heroTitle.style.fontSize = `${baseSize * 3}px`;

      const heroTagline = document.getElementById('hero-tagline');
      heroTagline.textContent = config.tagline || defaultConfig.tagline;
      heroTagline.style.color = config.text_color || defaultConfig.text_color;
      heroTagline.style.fontFamily = fontFamily;
      heroTagline.style.fontSize = `${baseSize * 1.25}px`;

      const primaryButtons = document.querySelectorAll('.btn-primary');
      primaryButtons.forEach(btn => {
        btn.style.backgroundColor = config.primary_action_color || defaultConfig.primary_action_color;
        btn.style.color = config.text_color || defaultConfig.text_color;
        btn.style.fontFamily = fontFamily;
        btn.style.fontSize = `${baseSize}px`;
      });

      const secondaryButtons = document.querySelectorAll('.btn-secondary');
      secondaryButtons.forEach(btn => {
        btn.style.backgroundColor = config.secondary_action_color || defaultConfig.secondary_action_color;
        btn.style.color = config.text_color || defaultConfig.text_color;
        btn.style.fontFamily = fontFamily;
        btn.style.fontSize = `${baseSize}px`;
      });

      const menuTitle = document.getElementById('menu-title');
      menuTitle.textContent = config.menu_title || defaultConfig.menu_title;
      menuTitle.style.color = config.text_color || defaultConfig.text_color;
      menuTitle.style.fontFamily = fontFamily;
      menuTitle.style.fontSize = `${baseSize * 2.5}px`;

      const sectionTitles = document.querySelectorAll('section h2');
      sectionTitles.forEach(title => {
        title.style.color = config.text_color || defaultConfig.text_color;
        title.style.fontFamily = fontFamily;
        title.style.fontSize = `${baseSize * 2.5}px`;
      });

      const categoryTitles = document.querySelectorAll('section h3');
      categoryTitles.forEach(title => {
        title.style.color = config.text_color || defaultConfig.text_color;
        title.style.fontFamily = fontFamily;
        title.style.fontSize = `${baseSize * 1.875}px`;
      });

      const menuCards = document.querySelectorAll('.menu-item-card');
      menuCards.forEach(card => {
        const bgColor = config.surface_color || defaultConfig.surface_color;
        card.style.backgroundColor = bgColor;
        card.style.color = config.text_color || defaultConfig.text_color;
        
        const cardTitle = card.querySelector('h4');
        if (cardTitle) {
          cardTitle.style.fontFamily = fontFamily;
          cardTitle.style.fontSize = `${baseSize * 1.25}px`;
        }
        
        const cardText = card.querySelectorAll('p');
        cardText.forEach(p => {
          p.style.fontFamily = fontFamily;
          p.style.fontSize = `${baseSize}px`;
        });
      });

      const formCards = document.querySelectorAll('.reservation-form-card, .contact-form-card, .delivery-card');
      formCards.forEach(card => {
        card.style.backgroundColor = config.surface_color || defaultConfig.surface_color;
        card.style.color = config.text_color || defaultConfig.text_color;
      });

      const labels = document.querySelectorAll('label');
      labels.forEach(label => {
        label.style.color = config.text_color || defaultConfig.text_color;
        label.style.fontFamily = fontFamily;
        label.style.fontSize = `${baseSize * 0.875}px`;
      });

      const inputs = document.querySelectorAll('input, select, textarea');
      inputs.forEach(input => {
        input.style.backgroundColor = config.background_color || defaultConfig.background_color;
        input.style.color = config.text_color || defaultConfig.text_color;
        input.style.borderColor = config.primary_action_color || defaultConfig.primary_action_color;
        input.style.fontFamily = fontFamily;
        input.style.fontSize = `${baseSize}px`;
      });

      const reviewCards = document.querySelectorAll('.review-card');
      reviewCards.forEach(card => {
        card.style.backgroundColor = config.surface_color || defaultConfig.surface_color;
        card.style.color = config.text_color || defaultConfig.text_color;
        
        const reviewText = card.querySelectorAll('p, h4');
        reviewText.forEach(text => {
          text.style.fontFamily = fontFamily;
          text.style.fontSize = `${baseSize}px`;
        });
      });

      const footer = document.querySelector('footer');
      footer.style.backgroundColor = config.surface_color || defaultConfig.surface_color;
      footer.style.color = config.text_color || defaultConfig.text_color;

      const footerText = document.getElementById('footer-text');
      footerText.textContent = config.footer_text || defaultConfig.footer_text;
      footerText.style.fontFamily = fontFamily;
      footerText.style.fontSize = `${baseSize * 0.875}px`;

      const deliveryPhone = document.getElementById('delivery-phone');
      deliveryPhone.textContent = `Llama al: ${config.contact_phone || defaultConfig.contact_phone}`;
      deliveryPhone.style.fontFamily = fontFamily;
      deliveryPhone.style.fontSize = `${baseSize * 1.25}px`;

      const allText = document.querySelectorAll('p, span, div');
      allText.forEach(text => {
        if (!text.style.fontSize) {
          text.style.fontFamily = fontFamily;
          text.style.fontSize = `${baseSize}px`;
        }
      });
    }

    function toggleTheme() {
      isDarkMode = !isDarkMode;
      const theme = isDarkMode ? darkTheme : lightTheme;
      
      const themeToggleBtn = document.getElementById('theme-toggle');
      const sunIcon = document.getElementById('sun-icon');
      const moonIcon = document.getElementById('moon-icon');
      
      if (isDarkMode) {
        sunIcon.classList.add('hidden');
        moonIcon.classList.remove('hidden');
        themeToggleBtn.style.backgroundColor = theme.surface;
        themeToggleBtn.style.color = theme.text;
      } else {
        moonIcon.classList.add('hidden');
        sunIcon.classList.remove('hidden');
        themeToggleBtn.style.backgroundColor = theme.surface;
        themeToggleBtn.style.color = theme.text;
      }
      
      if (window.elementSdk && window.elementSdk.config) {
        window.elementSdk.config.background_color = theme.background;
        window.elementSdk.config.surface_color = theme.surface;
        window.elementSdk.config.text_color = theme.text;
        window.elementSdk.setConfig({
          background_color: theme.background,
          surface_color: theme.surface,
          text_color: theme.text
        });
      } else {
        applyThemeDirectly(theme);
      }
    }

    function applyThemeDirectly(theme) {
      document.body.style.backgroundColor = theme.background;
      document.body.style.color = theme.text;
      
      const navbar = document.getElementById('navbar');
      navbar.style.backgroundColor = theme.surface;
      
      const navTitle = document.getElementById('nav-title');
      navTitle.style.color = theme.text;
      
      const navLinks = document.querySelectorAll('.nav-link');
      navLinks.forEach(link => {
        link.style.color = theme.text;
      });
      
      const sectionTitles = document.querySelectorAll('section h2, section h3, section h4');
      sectionTitles.forEach(title => {
        title.style.color = theme.text;
      });
      
      const menuCards = document.querySelectorAll('.menu-item-card');
      menuCards.forEach(card => {
        card.style.backgroundColor = theme.surface;
        card.style.color = theme.text;
      });
      
      const formCards = document.querySelectorAll('.reservation-form-card, .contact-form-card, .delivery-card, .review-card, .glass-effect');
      formCards.forEach(card => {
        card.style.backgroundColor = theme.surface;
        card.style.color = theme.text;
      });
      
      const inputs = document.querySelectorAll('input, select, textarea');
      inputs.forEach(input => {
        input.style.backgroundColor = theme.background;
        input.style.color = theme.text;
      });
      
      const footer = document.querySelector('footer');
      footer.style.backgroundColor = theme.surface;
      footer.style.color = theme.text;
    }

    async function initApp() {
      const themeToggleBtn = document.getElementById('theme-toggle');
      themeToggleBtn.addEventListener('click', toggleTheme);
      
      themeToggleBtn.style.backgroundColor = darkTheme.surface;
      themeToggleBtn.style.color = darkTheme.text;
      
      if (window.dataSdk) {
        const initResult = await window.dataSdk.init(dataHandler);
        if (!initResult.isOk) {
          console.error("Error al inicializar Data SDK");
        }
      }

      if (window.elementSdk) {
        window.elementSdk.init({
          defaultConfig,
          onConfigChange,
          mapToCapabilities: (config) => ({
            recolorables: [
              {
                get: () => config.background_color || defaultConfig.background_color,
                set: (value) => {
                  window.elementSdk.config.background_color = value;
                  window.elementSdk.setConfig({ background_color: value });
                }
              },
              {
                get: () => config.surface_color || defaultConfig.surface_color,
                set: (value) => {
                  window.elementSdk.config.surface_color = value;
                  window.elementSdk.setConfig({ surface_color: value });
                }
              },
              {
                get: () => config.text_color || defaultConfig.text_color,
                set: (value) => {
                  window.elementSdk.config.text_color = value;
                  window.elementSdk.setConfig({ text_color: value });
                }
              },
              {
                get: () => config.primary_action_color || defaultConfig.primary_action_color,
                set: (value) => {
                  window.elementSdk.config.primary_action_color = value;
                  window.elementSdk.setConfig({ primary_action_color: value });
                }
              },
              {
                get: () => config.secondary_action_color || defaultConfig.secondary_action_color,
                set: (value) => {
                  window.elementSdk.config.secondary_action_color = value;
                  window.elementSdk.setConfig({ secondary_action_color: value });
                }
              }
            ],
            borderables: [],
            fontEditable: {
              get: () => config.font_family || defaultConfig.font_family,
              set: (value) => {
                window.elementSdk.config.font_family = value;
                window.elementSdk.setConfig({ font_family: value });
              }
            },
            fontSizeable: {
              get: () => config.font_size || defaultConfig.font_size,
              set: (value) => {
                window.elementSdk.config.font_size = value;
                window.elementSdk.setConfig({ font_size: value });
              }
            }
          }),
          mapToEditPanelValues: (config) => new Map([
            ["restaurant_name", config.restaurant_name || defaultConfig.restaurant_name],
            ["tagline", config.tagline || defaultConfig.tagline],
            ["menu_title", config.menu_title || defaultConfig.menu_title],
            ["contact_phone", config.contact_phone || defaultConfig.contact_phone],
            ["contact_email", config.contact_email || defaultConfig.contact_email],
            ["footer_text", config.footer_text || defaultConfig.footer_text]
          ])
        });

        await onConfigChange(window.elementSdk.config);
      }

      setupReservationForm();
      setupContactForm();
      setupSmoothScrolling();
    }

    function setupReservationForm() {
      const form = document.getElementById('reservation-form');
      const submitBtn = document.getElementById('res-submit-btn');
      const submitText = document.getElementById('res-submit-text');
      const successMessage = document.getElementById('res-success-message');

      const today = new Date().toISOString().split('T')[0];
      document.getElementById('res-date').setAttribute('min', today);

      form.addEventListener('submit', async (e) => {
        e.preventDefault();

        if (recordCount >= 999) {
          successMessage.style.backgroundColor = '#fee2e2';
          successMessage.style.color = '#991b1b';
          successMessage.innerHTML = '<p class="font-semibold text-center">Límite de reservaciones alcanzado. Por favor contacta directamente al restaurante.</p>';
          successMessage.classList.remove('hidden');
          setTimeout(() => successMessage.classList.add('hidden'), 5000);
          return;
        }

        submitBtn.disabled = true;
        submitText.innerHTML = '<div class="loading-spinner"></div>';

        const formData = {
          id: Date.now().toString(),
          type: "reservation",
          name: document.getElementById('res-name').value,
          email: document.getElementById('res-email').value,
          phone: document.getElementById('res-phone').value,
          guests: parseInt(document.getElementById('res-guests').value),
          date: document.getElementById('res-date').value,
          time: document.getElementById('res-time').value,
          message: "",
          createdAt: new Date().toISOString()
        };

        if (window.dataSdk) {
          const result = await window.dataSdk.create(formData);
          
          submitBtn.disabled = false;
          submitText.textContent = 'Reservar Ahora';

          if (result.isOk) {
            form.reset();
            successMessage.style.backgroundColor = '#d1fae5';
            successMessage.style.color = '#065f46';
            successMessage.innerHTML = '<p class="font-semibold text-center">¡Reservación confirmada! Te enviaremos un email de confirmación.</p>';
            successMessage.classList.remove('hidden');
            setTimeout(() => successMessage.classList.add('hidden'), 5000);
          } else {
            successMessage.style.backgroundColor = '#fee2e2';
            successMessage.style.color = '#991b1b';
            successMessage.innerHTML = '<p class="font-semibold text-center">Error al procesar la reservación. Intenta nuevamente.</p>';
            successMessage.classList.remove('hidden');
            setTimeout(() => successMessage.classList.add('hidden'), 5000);
          }
        }
      });
    }

    function setupContactForm() {
      const form = document.getElementById('contact-form');
      const submitBtn = document.getElementById('contact-submit-btn');
      const submitText = document.getElementById('contact-submit-text');
      const successMessage = document.getElementById('contact-success-message');

      form.addEventListener('submit', async (e) => {
        e.preventDefault();

        if (recordCount >= 999) {
          successMessage.style.backgroundColor = '#fee2e2';
          successMessage.style.color = '#991b1b';
          successMessage.innerHTML = '<p class="font-semibold text-center">Límite de mensajes alcanzado. Por favor contacta directamente al restaurante.</p>';
          successMessage.classList.remove('hidden');
          setTimeout(() => successMessage.classList.add('hidden'), 5000);
          return;
        }

        submitBtn.disabled = true;
        submitText.innerHTML = '<div class="loading-spinner"></div>';

        const formData = {
          id: Date.now().toString(),
          type: "contact",
          name: document.getElementById('contact-name').value,
          email: document.getElementById('contact-email').value,
          phone: "",
          date: "",
          time: "",
          guests: 0,
          message: document.getElementById('contact-message').value,
          createdAt: new Date().toISOString()
        };

        if (window.dataSdk) {
          const result = await window.dataSdk.create(formData);
          
          submitBtn.disabled = false;
          submitText.textContent = 'Enviar Mensaje';

          if (result.isOk) {
            form.reset();
            successMessage.style.backgroundColor = '#d1fae5';
            successMessage.style.color = '#065f46';
            successMessage.innerHTML = '<p class="font-semibold text-center">¡Mensaje enviado! Te responderemos pronto.</p>';
            successMessage.classList.remove('hidden');
            setTimeout(() => successMessage.classList.add('hidden'), 5000);
          } else {
            successMessage.style.backgroundColor = '#fee2e2';
            successMessage.style.color = '#991b1b';
            successMessage.innerHTML = '<p class="font-semibold text-center">Error al enviar el mensaje. Intenta nuevamente.</p>';
            successMessage.classList.remove('hidden');
            setTimeout(() => successMessage.classList.add('hidden'), 5000);
          }
        }
      });
    }

    function setupSmoothScrolling() {
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function (e) {
          e.preventDefault();
          const target = document.querySelector(this.getAttribute('href'));
          if (target) {
            target.scrollIntoView({ behavior: 'smooth', block: 'start' });
          }
        });
      });
    }

    initApp();
  </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9a8d33f3361f8a88',t:'MTc2NDg3MTIyMi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
