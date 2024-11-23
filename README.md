# andyknow
import matplotlib.pyplot as plt
import networkx as nx

# Crear el grafo para el mapa mental
G = nx.DiGraph()

# Agregar nodos principales y secundarios al mapa mental
nodes = {
    "Technological Evolution and Robotics": [
        "I. History of Robotics",
        "II. Types of Robots",
        "III. Key Technologies in Robotics",
        "IV. Applications",
        "V. Challenges and Future Prospects"
    ],
    "I. History of Robotics": [
        "Ancient Foundations",
        "Industrial Revolution",
        "20th Century Advancements"
    ],
    "II. Types of Robots": [
        "Industrial Robots",
        "Service Robots",
        "Humanoid Robots",
        "Exploration Robots"
    ],
    "III. Key Technologies in Robotics": [
        "Artificial Intelligence",
        "Sensors and Perception",
        "Actuators",
        "Control Systems"
    ],
    "IV. Applications": [
        "Manufacturing",
        "Healthcare",
        "Agriculture",
        "Entertainment",
        "Military"
    ],
    "V. Challenges and Future Prospects": [
        "Ethical Concerns",
        "Technical Challenges",
        "Future Trends"
    ]
}

# Crear relaciones jerárquicas
for parent, children in nodes.items():
    for child in children:
        G.add_edge(parent, child)

# Configuración del layout del grafo para mapa mental
pos = nx.spring_layout(G, seed=42)

# Dibujar el mapa mental
plt.figure(figsize=(15, 10))
nx.draw(
    G, pos, with_labels=True, 
    node_size=4000, node_color="#A8DADC", 
    font_size=9, font_weight="bold", 
    edge_color="#457B9D", arrowsize=15, 
    alpha=0.9
)
plt.title("Mind Map: Technological Evolution and Robotics", fontsize=18, fontweight="bold", color="#1D3557")
plt.show()
