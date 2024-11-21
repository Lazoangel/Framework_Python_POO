print ("Lazo Jimenez Angel Jesus 3W")
class Persona:
    """
    Clase que representa a una persona con nombre, edad y DNI.
    Permite mostrar los datos y verificar si es mayor de edad.
    """
    
    def __init__(self, nombre="", edad=None, dni=""):
        """Inicializa la persona con los atributos proporcionados."""
        self.nombre = nombre
        self.edad = edad
        self.dni = dni

    @property
    def nombre(self): return self._nombre

    @nombre.setter
    def nombre(self, valor): self._nombre = valor if valor else ""

    @property
    def edad(self): return self._edad

    @edad.setter
    def edad(self, valor): self._edad = valor if isinstance(valor, int) and valor >= 0 else None

    @property
    def dni(self): return self._dni

    @dni.setter
    def dni(self, valor): self._dni = valor if len(valor) == 9 and valor[:-1].isdigit() and valor[-1].isalpha() else ""

    def mostrar(self):
        """Muestra los datos de la persona."""
        print(f"Nombre: {self.nombre}, Edad: {self.edad}, DNI: {self.dni}")

    def esMayorDeEdad(self):
        """Devuelve True si la persona tiene 18 o más años."""
        return self.edad >= 18 if self.edad is not None else False


# Ejemplo de uso
persona1 = Persona("Lazo", 16, "12345678A")
persona1.mostrar()  # Muestra los datos
print(persona1.esMayorDeEdad())  # Devuelve True

![image](https://github.com/user-attachments/assets/ec8e6aa9-8db9-4628-9038-e0164a90a651)
