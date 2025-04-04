# candy-shape-generator
import matplotlib.pyplot as plt
import numpy as np
import random

def draw_candy(shape="circle"):
    fig, ax = plt.subplots()
    ax.set_aspect('equal')
    ax.set_xticks([])
    ax.set_yticks([])
    ax.set_xlim(-1.5, 1.5)
    ax.set_ylim(-1.5, 1.5)
    
    if shape == "circle":
        circle = plt.Circle((0, 0), 1, color=random.choice(["red", "blue", "green", "yellow", "pink"]))
        ax.add_patch(circle)
    elif shape == "square":
        square = plt.Rectangle((-1, -1), 2, 2, color=random.choice(["orange", "purple", "brown"]))
        ax.add_patch(square)
    elif shape == "heart":
        t = np.linspace(0, 2 * np.pi, 100)
        x = 0.5 * np.sin(t) ** 3
        y = 0.5 * (0.8125 * np.cos(t) - 0.3125 * np.cos(2*t) - 0.125 * np.cos(3*t) - 0.0625 * np.cos(4*t))
        ax.fill(x, y, color=random.choice(["red", "pink", "purple"]))
    elif shape == "star":
        theta = np.linspace(0, 2*np.pi, 10)
        r = np.array([1, 0.4, 0.8, 0.4, 0.8, 0.4, 0.8, 0.4, 1, 0.4])
        x = r * np.cos(theta)
        y = r * np.sin(theta)
        ax.fill(x, y, color=random.choice(["gold", "yellow", "orange"]))
    else:
        print("Unknown shape! Available: circle, square, heart, star")
        return
    
    plt.title(f"Candy Shape: {shape.capitalize()}")
    plt.show()

# Example usage
draw_candy("heart")
yuo
