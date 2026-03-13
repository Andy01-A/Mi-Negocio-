# Mi-Negocio-
De lo bueno simplemente lo mejor 
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Negocio Digital</title>
    <style>
        /* CSS: Aquí definimos el diseño y colores */
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }
        header {
            background-color: #2c3e50;
            color: white;
            padding: 20px;
            text-align: center;
        }
        .container {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            padding: 20px;
        }
        .card {
            background: white;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            margin: 15px;
            width: 250px;
            text-align: center;
            padding: 15px;
            transition: transform 0.3s;
        }
        .card:hover {
            transform: translateY(-5px);
        }
        .price {
            color: #27ae60;
            font-size: 1.2em;
            font-weight: bold;
        }
        button {
            background-color: #25d366;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1em;
        }
        button:hover {
            background-color: #128c7e;
        }
    </style>
</head>
<body>

<header>
    <h1>Catálogo de Mi Negocio</h1>
    <p>Calidad y confianza a un clic</p>
</header>

<div class="container" id="catalogo">
    </div>

<script>
    /* JavaScript: Aquí manejamos la lógica y los datos */
    
    // 1. Lista de productos (puedes cambiar los nombres y precios aquí)
    const productos = [
        { nombre: "LECHUGA", precio: "$210.00", descripcion: "Excelente calidad" },
        { nombre: "huevos", precio: "$560.00", descripcion: "El más vendido" },
        { nombre: "JALAPEÑOS", precio: "$25.00", descripcion: "Edición limitada" }
    ];

    const contenedor = document.getElementById('catalogo');

    // 2. Función para mostrar productos en la pantalla
    productos.forEach(item => {
        const card = document.createElement('div');
        card.className = 'card';
        card.innerHTML = `
            <h3>${item.nombre}</h3>
            <p>${item.descripcion}</p>
            <p class="price">${item.precio}</p>
            <button onclick="realizarPedido('${item.nombre}')">Pedir por WhatsApp</button>
        `;
        contenedor.appendChild(card);
    });

    // 3. Función para enviar mensaje a WhatsApp
    function realizarPedido(nombreProducto) {
        const telefono = "+5281 2200 7126"; // Reemplaza con tu número (incluye código de país)
        const mensaje = encodeURIComponent(`Hola, me interesa comprar el ${nombreProducto}`);
        window.open(`https://wa.me/${telefono}?text=${mensaje}`, '_blank');
    }
</script>

</body>
</html>
