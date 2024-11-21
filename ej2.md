print ("Lazo Jimenez Angel Jesus 3W")
class Cuenta:

    def __init__(self, titular, cantidad=0.0):

        self.titular = titular  # El titular debe ser una instancia de Persona
        self._cantidad = cantidad  # La cantidad se establece en el constructor

    @property
    def cantidad(self):
        return self._cantidad

    def mostrar(self):

        print(f"Titular: {self.titular.nombre}, Cantidad: {self.cantidad}€")

    def ingresar(self, cantidad):
        if cantidad > 0:
            self._cantidad += cantidad  # Solo se ingresa dinero si es positivo

    def retirar(self, cantidad):
        if cantidad > 0:
            self._cantidad -= cantidad  # Se puede retirar independientemente del saldo


# Ejemplo de uso
class Persona:
    def __init__(self, nombre):
        self.nombre = nombre

# Crear un titular de la cuenta (persona)
persona1 = Persona("Lazo")

# Crear la cuenta con la persona como titular y un saldo inicial de 100.0€
cuenta1 = Cuenta(persona1, 100.0)

# Mostrar los datos de la cuenta
cuenta1.mostrar()  # Muestra: Titular: Lazo, Cantidad: 100.0€

# Ingresar dinero en la cuenta
cuenta1.ingresar(50.0)
cuenta1.mostrar()  # Muestra: Titular: Lazo, Cantidad: 150.0€

# Retirar dinero de la cuenta
cuenta1.retirar(30.0)
cuenta1.mostrar()  # Muestra: Titular: Lazo, Cantidad: 120.0€
![image](https://github.com/user-attachments/assets/7fbe3bfe-f8e9-4817-9523-9329629b4881)
