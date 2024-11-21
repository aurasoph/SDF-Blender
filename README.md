# Signed Distance Functions in Blender using Volume Cube Node

This repository provides a basic overview of Signed Distance Functions (SDFs) implemented using Blender's **Volume Cube** node (and **Volume to Mesh** node). SDFs represent objects mathematically by measuring the signed distance from any point in space to the closest point on a surface. This technique enables efficient visualization and manipulation of 3D objects.

> **Note**: Majority of the functions work in Blender 3.6+, but the **Mesh -> SDF** node requires Blender 4.0. A fully 3.6-compatible version will be released in the future.

---

## Overview

### **Cover Example**
Demonstrates smooth mixing between:
- A mesh converted to an SDF (Rock)
- A primitive SDF function (Sphere)

---

## **Functions**

### **1. Signed Distance Functions (SDFs)**

#### **Cylinder SDF**
Represents a cylinder using the signed distance from the surface.

#### **Sphere SDF**
Defines a sphere as a signed distance function.

#### **Box (Cube) SDF**
Represents a cube using signed distance calculations.

---

### **2. Mesh to Distance**
Converts a mesh into an SDF.

- **Functionality**: Determines if a point is inside or outside the mesh.
- **4.0 Compatibility**: Utilizes "samples" to evaluate multiple points for accurate results.
- **3.6 Compatibility**: Lacks sample-based precision, leading to potential inaccuracies.

> **Limitations**: Struggles with complex meshes; improvements are planned for future updates.

---

### **3. Combine Operations**
Allows combining or modifying SDFs using various mathematical operations:

- **Intersection**: Represents only the overlapping area by taking the maximum of the two SDFs.
- **Difference**: Subtracts one SDF from another.
- **Union**: Combines two SDFs into a single representation.
- **Smooth Mix**: Similar to Union, but blends the intersection smoothly.

---

### **4. SDF to Density**
Converts SDFs into a density function for processing within the **Volume Cube Node**.

---

### **5. Bound Control**
Defines the bounds for the Volume Cube Node to avoid infinite calculations.

- **Combine Bounds**: Expands bounds to include both SDFs when combining them.
- **Expand Bounds**: Manually increases the bounds for specific requirements.

---

### **6. Density to Mesh**
Processes density data into a mesh using the **Volume Cube Node**.

- Inputs density and bounds to create a mesh representation of the SDF.

---

## Notes on Blender Compatibility

- Blender 3.6+: Majority of the functions are supported.
- Blender 4.0+: Introduces sample-based evaluation in the **Mesh to Distance** function, enabling more accurate conversions.