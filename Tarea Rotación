import numpy as np
import math


def rotar_x(x, y, z, angulo):
    """
    Aplica una rotación alrededor del eje X.

    Parámetros:
        x (float): componente en X del vector
        y (float): componente en Y del vector
        z (float): componente en Z del vector
        angulo (float): ángulo de rotación en grados

    Retorna:
        np.ndarray: vector rotado respecto al eje X
    """
    rad = math.radians(angulo)
    matriz = np.array([
        [1, 0, 0],
        [0, math.cos(rad), -math.sin(rad)],
        [0, math.sin(rad), math.cos(rad)]
    ])
    return matriz @ np.array([x, y, z])


def rotar_y(x, y, z, angulo):
    """
    Aplica una rotación alrededor del eje Y.
    """
    rad = math.radians(angulo)
    matriz = np.array([
        [math.cos(rad), 0, math.sin(rad)],
        [0, 1, 0],
        [-math.sin(rad), 0, math.cos(rad)]
    ])
    return matriz @ np.array([x, y, z])


def rotar_z(x, y, z, angulo):
    """
    Aplica una rotación alrededor del eje Z.
    """
    rad = math.radians(angulo)
    matriz = np.array([
        [math.cos(rad), -math.sin(rad), 0],
        [math.sin(rad), math.cos(rad), 0],
        [0, 0, 1]
    ])
    return matriz @ np.array([x, y, z])


def rotar_vector(x, y, z, angulo, eje):
    """
    Determina el eje de rotación y aplica la transformación.

    Parámetros:
        x, y, z (float): componentes del vector original
        angulo (float): ángulo en grados
        eje (str): 'X', 'Y' o 'Z' indicando el eje de rotación

    Retorna:
        np.ndarray: vector rotado
    """
    eje = eje.upper()
    if eje == "X":
        return rotar_x(x, y, z, angulo)
    elif eje == "Y":
        return rotar_y(x, y, z, angulo)
    elif eje == "Z":
        return rotar_z(x, y, z, angulo)
    else:
        raise ValueError("El eje debe ser 'X', 'Y' o 'Z'.")


if __name__ == "__main__":
    coords = input("Ingrese las 3 coordenadas del vector separadas por espacio: ")
    angulo = float(input("Ingrese el ángulo de rotación (en grados): "))
    eje = input("Ingrese el eje de rotación (X, Y o Z): ")

    x, y, z = map(float, coords.split())
    print("Vector resultante:", rotar_vector(x, y, z, angulo, eje))
