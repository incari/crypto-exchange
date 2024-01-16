# Prueba técnica Bitnovo

### Demo

[Demo](https://crypto-exchange-dun-psi.vercel.app/)

## Descripción

El desarrollo consiste en crear una pasarela de pago con criptodivisas. Esta se va a realizar en un entorno de testnet. Toda la documentación de los endpoints y los contratos de las criptodivisas de testnet la podemos encontrar aquí.

En el Header de los endpoints tendrá que pasarle el Identificador (X-Device-Id) que te hayamos proporcionado por email para poder crear pagos.

Debe regirse estrictamente por el desarrollo de Figma. Utilizar react.js con hooks, y nextjs pages router.

El desarrollo principal consiste en:

1. **Crear pago y selección de moneda**  
   El Merchant deberá poder crear un pago añadiendo el importe, concepto y criptodivisa. Para crear el pago se hará uso del endpoint `POST orders` y para listar las criptodivisas disponibles se hará con el endpoint `GET currencies`. Los 3 campos mencionados anteriormente deberán introducirse en una misma pantalla y las criptodivisas que se podrán seleccionar para crear el pago variarán en función del importe del pago. Hay que controlar el importe máximo y mínimo de cada moneda.

2. **Pasarela de pago QR**  
   Una vez el pago esté creado debemos mostrar todos los datos del resumen del pago y la información para que el Cliente pueda realizarlo. Todos estos datos los podemos obtener haciendo uso del endpoint `GET orders/info`.  
   Importante: la pasarela de pago debe refrescarse en tiempo real, es decir, si se recibe un pago la pantalla se debe refrescar de forma automática. Al crear un pago, se crea un websocket el cual se puede escuchar para recibir notificaciones de cambio de estado.
   Ejemplo de websocket:  
   `const socket = new WebSocket('wss://payments.pre-bnvo.com/ws/<identifier>');`  
   Sim
