# semana6
#Este programa se basa en un supermercado, donde me muestra los productos y los productos de primera necesidad
#
# Definición de la clase base Producto
class Producto:
    def __init__(self, nombre, marca, costo):
        self._nombre = nombre  # Encapsulación del atributo nombre
        self.marca = marca  # Atributo público marca
        self.costo = costo  # Atributo público costo

    def mostrar_informacion(self):
        """Método para mostrar la información del producto."""
        return f"Producto: {self._nombre}, Marca: {self.marca}, Costo: ${self.costo:.2f}"


# Definición de una subclase de Producto para productos de primera necesidad
class ProductoPrimeraNecesidad(Producto):
    def __init__(self, nombre, marca, costo, fecha_caducidad):
        super().__init__(nombre, marca, costo)
        self.__fecha_caducidad = fecha_caducidad  # Encapsulación del atributo fecha_caducidad

    # Método polimórfico: sobrescribe el método de la clase base
    def mostrar_informacion(self):
        """Método para mostrar la información del producto de primera necesidad."""
        return f"Producto de Primera Necesidad: {self._nombre}, Marca: {self.marca}, Costo: ${self.costo:.2f}, Fecha de Caducidad: {self.__fecha_caducidad}"


# Función principal para probar el programa
def main():
    # Creación de instancias de productos
    producto_generico = Producto("Shampoo", "Pantene", 150.50)
    producto_primera_necesidad = ProductoPrimeraNecesidad("Leche", "Lala", 30.75, "2024-07-15")

    # Demostración de polimorfismo llamando al método mostrar_informacion
    print(producto_generico.mostrar_informacion())  # Llama al método de Producto
    print(producto_primera_necesidad.mostrar_informacion())  # Llama al método de ProductoPrimeraNecesidad


# Ejecución del programa principal
if __name__ == "__main__":
    main()
