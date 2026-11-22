# Python-Garbage-Collection

import gc
import sys

# Display garbage collector status
print("Garbage Collection Enabled:", gc.isenabled())

# Function to demonstrate object creation
class Demo:
    def __init__(self, name):
        self.name = name

    def __del__(self):
        print(self.name, "object destroyed")


# Creating objects
print("\nCreating objects...")
obj1 = Demo("Object 1")
obj2 = Demo("Object 2")

# Display reference count
print("\nReference count of obj1:", sys.getrefcount(obj1))

# Removing references
print("\nDeleting objects...")
del obj1
del obj2

# Manual garbage collection
print("\nRunning garbage collector...")
collected = gc.collect()

print("Garbage collected objects:", collected)

# Garbage collector information
print("\nGarbage Collector Statistics:")
print(gc.get_stats())

# Disable garbage collection
gc.disable()
print("\nGarbage Collection Enabled:", gc.isenabled())

# Enable garbage collection
gc.enable()
print("Garbage Collection Enabled:", gc.isenabled())

print("\nGarbage collection demonstration completed!")
