# exp.no: 11 .record-IMPLEMENTATION-OF-HUFFMAN-CODING
# Aim
To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

Morphological Opening Morphological Closing

# Software Used
Anaconda – Python 3.7 Jupyter Notebook / VS Code OpenCV (cv2) NumPy Matplotlib

# Algorithm
Step 1: Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2: Create or load an input image containing foreground objects.

Step 3: Display the original image.

Step 4: Create a structuring element (kernel) of suitable size.

Step 5: Opening Operation Apply the Opening operation using the structuring element. Opening consists of Erosion followed by Dilation. Remove small foreground noises while preserving the shape of larger objects. Display the opened image.

Step 6: Closing Operation Apply the Closing operation using the structuring element. Closing consists of Dilation followed by Erosion. Fill small holes and gaps within foreground objects. Display the closed image.

Step 7: Compare the original, opened, and closed images.

# program

```
input_string = "LIDISON SHAM M (212224040171)"  # Example input string
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1
nodes = [[char, freq] for char, freq in frequency.items()]
while len(nodes) > 1:
    # Sort nodes based on frequency
    nodes = sorted(nodes, key=lambda x: x[1])

    # Pick two smallest nodes
    left = nodes.pop(0)
    right = nodes.pop(0)

    # Create a new node with combined frequency
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)

# The final node is the Huffman tree
huffman_tree = nodes[0]
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)
print("Character |LIDISON SHAM M (212224040171) ")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")

```
    
# output
<img width="293" height="265" alt="WhatsApp Image 2026-09-23 at 12 06 42 AM" src="https://github.com/user-attachments/assets/3b2d788d-8c15-4be2-a6ec-209cd1090e27" />

# result
Thus, huffman code successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
