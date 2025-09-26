from abc import ABC, abstractmethod
import math

class Figura(ABC):
    @abstractmethod
    def calcular_perimetro(self) -> float:
        pass

    @abstractmethod
    def calcular_area(self) -> float:
        pass

    @abstractmethod
    def obtener_nombre(self) -> str:
        pass

class TrianguloEquilatero(Figura):
    def __init__(self, lado: float):
        self.lado = lado

    def calcular_perimetro(self) -> float:
        return 3 * self.lado

    def calcular_area(self) -> float:
        return (math.sqrt(3) / 4) * (self.lado ** 2)

    def obtener_nombre(self) -> str:
        return "Triángulo"

if __name__ == "__main__":
    t = TrianguloEquilatero(6)
    print(t.obtener_nombre())
    print(f"Perímetro: {t.calcular_perimetro():.2f}")
    print(f"Área: {t.calcular_area():.2f}")
