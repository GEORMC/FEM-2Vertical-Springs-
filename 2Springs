import numpy as np

# Define the spring constants
k1 = 100
k2 = 200

# Define the nodal coordinate matrix
node_coordinates = np.array([[0, 0], [1, 0], [2, 0]])

# Define the node connectivity matrix
node_connectivity = np.array([[1, 2], [2, 3]])

# Define the force vector
force_vector = np.array([0, 0, 100])

# Calculate the global stiffness matrix
global_stiffness_matrix = np.zeros((3, 3))
for i in range(3):
    for j in range(3):
        if i == j:
            global_stiffness_matrix[i, j] = k1 + k2
        elif node_connectivity[i, 0] == j:
            global_stiffness_matrix[i, j] = -k1
        elif node_connectivity[i, 1] == j:
            global_stiffness_matrix[i, j] = -k2

# Solve for the displacements
displacement_vector = np.linalg.solve(global_stiffness_matrix, force_vector)

# Print the displacements
print(displacement_vector)
