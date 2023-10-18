# Python Composite Design Pattern

## Table of Contents

- [Definition](#definition)
- [Explanation in Simple Terms](#explanation-in-simple-terms)
- [Code Related Explanation](#code-related-explanation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Definition

The Composite Design Pattern is a structural design pattern that allows you to compose objects into tree structures to represent part-whole hierarchies. It lets clients treat individual objects and compositions of objects uniformly, making it easier to work with complex structures.

## Explanation in Simple Terms

Think of a file system. You have files and folders. Folders can contain both files and subfolders. The Composite pattern allows you to work with files and folders in a consistent way. You can perform operations on a single file or on a folder that contains multiple files and subfolders.

## Code Related Explanation

In this repository, we've provided a Python example to demonstrate the Composite Design Pattern. We have a `Component` class that defines a common interface for leaf nodes (e.g., files) and composite nodes (e.g., folders). Leaf nodes and composite nodes both implement this interface. This pattern allows you to create a hierarchy of objects and perform operations on them uniformly.

## Usage

You can use this repository to understand how the Composite Design Pattern works in Python. Clone the repository and explore the code to see how the pattern is implemented.

```python
# Example usage:
file1 = File("file1.txt")
file2 = File("file2.txt")
folder1 = Folder("Folder 1")
folder1.add(file1)
folder2 = Folder("Folder 2")
folder2.add(file2)
folder1.add(folder2)
