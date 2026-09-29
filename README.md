Ejercicio 2.E.2 09 - Interacción por Paso de Mensajes (GiftCard y Cliente)

Lógica del programa
Para resolver este ejercicio, trabajé con la interacción entre objetos mediante el envío de mensajes y el paso de referencias. Para lograrlo, diseñé dos clases complementarias: `GiftCard` y `Cliente`.

Primero, desarrollé la clase `GiftCard` aplicando encapsulamiento sobre sus atributos `codigo` (String) y `saldo` (double). Implementé el método `descontarSaldo(double monto)` que utiliza una estructura condicional (`if/else`) para verificar si los fondos son suficientes; si lo son, efectúa el descuento, imprime el comprobante y retorna `true`, caso contrario, la operación se cancela y retorna `false`.

Luego, diseñé la clase `Cliente`. El aspecto central de esta clase es que posee como atributo una referencia directa a un objeto del tipo `GiftCard`. Implementé el método `realizarCompra(double monto)`, el cual delega la responsabilidad: no realiza cálculos matemáticos propios, sino que interactúa enviándole el mensaje `descontarSaldo(monto)` a su tarjeta asociada.

En la clase `Main`, desarrollé la siguiente lógica de prueba:
1. Instancié un objeto `GiftCard` con saldo inicial de 5000.0 y un objeto `Cliente` ("Jorge"), pasándole la referencia de la tarjeta por parámetro en el constructor para vincularlos.
2. Instancié un segundo par de objetos, vinculando a un cliente ("Nicolas") con una tarjeta de saldo menor (670.0).
3. Efectué una prueba exitosa llamando al método `realizarCompra(350.0)` desde el primer cliente.
4. Forcé una prueba fallida llamando a `realizarCompra(1500.0)` desde el segundo cliente, comprobando por consola que la tarjeta rechaza el descuento por falta de saldo, demostrando que la comunicación entre ambos objetos funciona correctamente.

Ejecución en consola
<img width="1917" height="1020" alt="image" src="https://github.com/user-attachments/assets/87583677-5cac-42eb-986a-b249be9da865" />
