# Huffman-Coding
## Aim
To implement Huffman coding to compress the data using Python.

Software Required
Anaconda - Python 3.7

## Algorithm:
### Step1:
Get the input string
### Step2:
Calculate frequency of each character in the input string
### Step3:
Create tree nodes
### Step4:
Main function to implement Huffman coding
### Step5:
Generate Huffman codes
### Step 6: 
Print the characters and their Huffman codes

## Program:
```
input_string = "shubnum fathima faizoodin"

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

huffman_tree = nodes[0]

huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):  # If it's a leaf node
        huffman_codes[tree[0]] = code
    else:  # If it's an internal node, recurse
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)

print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")
```

## Output:
<img width="282" height="360" alt="image" src="https://github.com/user-attachments/assets/3bbebaee-3d5c-4df1-999f-f309dfedbaf8" />

## Result
Thus the huffman coding was implemented to compress the data using python programming.
