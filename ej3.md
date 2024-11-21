class Cuenta:
    print ("Lazo Jimenez Angel Jesus 3W")
    
    def __init__(self, titular, cantidad=0.0):
        self.titular = titular
        self._cantidad = cantidad

    @property
    def cantidad(self):
        return self._cantidad

    def mostrar(self):
        print(f"Titular: {self.titular.nombre}, Cantidad: {self.cantidad}€")

    def ingresar(self, cantidad):
        if cantidad > 0:
            self._cantidad += cantidad

    def retirar(self, cantidad):
        if cantidad > 0:
            self._cantidad -= cantidad


class CuentaJoven(Cuenta):

    def __init__(self, titular, cantidad=0.0, bonificacion=0.0):
        super().__init__(titular, cantidad)
        self.bonificacion = bonificacion

    @property
    def bonificacion(self):
        return self._bonificacion

    @bonificacion.setter
    def bonificacion(self, valor):
        if 0 <= valor <= 100:
            self._bonificacion = valor
        else:
            print("Bonificación inválida.")

    def esTitularValido(self):
        return 18 <= self.titular.edad < 25

    def mostrar(self):
        print(f"Cuenta Joven - Titular: {self.titular.nombre}, Cantidad: {self.cantidad}€, Bonificación: {self.bonificacion}%")

    def retirar(self, cantidad):
        if self.esTitularValido():
            super().retirar(cantidad)
        else:
            print("El titular no es válido para retirar dinero.")


# Clase Persona para crear el titular de la cuenta
class Persona:
    
    def __init__(self, nombre, edad):
        
        self.nombre = nombre
        self.edad = edad

# Ejemplo de uso
persona1 = Persona("Juan", 22)
cuenta1 = CuentaJoven(persona1, 100.0, 5.0)
cuenta1.mostrar()
cuenta1.retirar(50.0)

persona2 = Persona("Maria", 30)
cuenta2 = CuentaJoven(persona2, 200.0, 10.0)
cuenta2.mostrar()
cuenta2.retirar(50.0)  # No puede retirar porque el titular tiene más de 25 años
![image](https://github.com/user-attachments/assets/2a7b8918-17f0-4d8f-8355-f38598844c13)
