## The Assignment

Summary - Design and implement a web-based Multi-level Bill of Materials (BOM) Management System with the following features:

- Create, edit, and visualize complex multi-level BOM structures.
- Perform BOM operations such as explosion, implosion.
- Analyze component usage across different products.

# Example Case: Electric Bicycle Manufacturing

Imagine you're building a BOM Management System for an electric bicycle manufacturer, "EcoCycle Inc." They produce various models of e-bikes, each with multiple components and sub-assemblies.

## Sample Product: EcoRider Pro

The EcoRider Pro is a high-end electric bicycle with the following main components:

### Product - EcoRider Pro (Electric Bicycle)

- Frame Assembly Pro
    - Main Frame MF100001 - (Qty: 1)
    - Front Fork FF100002 - (Qty: 1)
    - Rear Shock RS100003 - (Qty: 1)
- Drivetrain Pro
    - Electric Motor EM100001 - (Qty: 1)
    - Battery Pack BP100002 - (Qty: 1)
    - Controller CO100003 - (Qty: 1)
    - Pedals PE100004 - (Qty: 2)
    - Chain CH100005 - (Qty: 1)
    - Gears GE100006 - (Qty: 1)
- Wheel Set Pro
    - Front Wheel FW100001 - (Qty: 1)
        - Rim RM100002 - (Qty: 1)
        - Spokes SP100003 - (Qty: 32)
        - Hub HB100004 - (Qty: 1)
        - Tire TR100005 - (Qty: 1)
    - Rear Wheel RW100001 - (Qty: 1)
        - Rim RM100002 - (Qty: 1)
        - Spokes SP100003 - (Qty: 32)
        - Hub HB100004 - (Qty: 1)
        - Tire TR100005 - (Qty: 1)
- Braking System Pro
    - Brake Levers BL100001 - (Qty: 2)
    - Brake Cables BC100002 - (Qty: 2)
    - Disc Brakes DB100003 - (Qty: 2)
- Cockpit Pro
    - Handlebars HB100001 - (Qty: 1)
    - Stem ST100002 - (Qty: 1)
    - Grips GR100003 - (Qty: 2)
    - Display Unit DU100004 - (Qty: 1)

## Tasks

Using this example, demonstrate the following in your BOM Management System:

1. Create a UI which should allow creating multi-level BOMs (something like the EcoRider Pro, including all components and sub-assemblies)
2. Implement a feature to add a new component (e.g., a bike light) to the BOM.
3. Show how to perform a BOM explosion to list all individual components needed to build 100 EcoRider Pro bikes.
4. Implement a BOM implosion to determine which finished products use a specific component (e.g., which bike models use the particular electric motor in the EcoRider Pro).
5. Demonstrate how to update the quantity of a component (e.g., changing the battery pack) and propagate this change through the BOM.
6. Implement a search function to quickly find components across all product BOMs.

## Technical Requirements

### Frontend (React)

- Implement a responsive UI for BOM management:
    - Tree view for visualizing multi-level BOMs
    - Form for adding/editing BOM items
    - Search functionality for finding components
- Create an interactive BOM explorer with expand/collapse and drag-and-drop functionality

### Backend (Node.js)

- Design and implement RESTful APIs for BOM operations (CRUD, tree traversal, manipulation)
- Implement efficient algorithms for BOM explosion, implosion.
- Design an efficient database schema for representing multi-level BOMs
- Implement data validation to ensure BOM integrity (e.g., preventing circular references)
- Ensure proper error handling and logging

## Evaluation Criteria

1. Code quality and organization
2. Efficiency of algorithms for BOM operations
3. Database design and query optimization
4. UI/UX considerations for managing complex hierarchical data
5. Error handling and edge case management
6. API design and implementation
7. Documentation quality
8. Test coverage and quality

## Submission Guidelines

1. Provide a link to a Git repository with the complete project
2. Deploy a demo version and provide the URL

# Bill of Materials (BOM) Concepts

## What is a Bill of Materials (BOM)?

A Bill of Materials (BOM) is a comprehensive list of raw materials, components, sub-assemblies, and other items required to create a product. It includes information such as part numbers, quantities, units of measure, and sometimes costs. BOMs are crucial in manufacturing, engineering, and supply chain management.

## BOM Structures

1. **Single-level BOM**: Lists only the components directly required to make the product.
2. **Multi-level BOM**: Shows the hierarchical relationship between all components, sub-assemblies, and the final product.

## Key BOM Concepts

### 1. BOM Levels

BOMs are often structured in levels, with the finished product at the top (level 0) and components at lower levels.

Example:

- Level 0: Bicycle
    - Level 1: Frame
    - Level 1: Wheel Set
        - Level 2: Front Wheel
            - Level 3: Rim
            - Level 3: Spokes
            - Level 3: Hub
        - Level 2: Rear Wheel
    - Level 1: Drivetrain

### 2. BOM Explosion

BOM explosion is the process of expanding a BOM to show all individual components required to build a product. It's useful for determining total material requirements for production planning.

Example:
Exploding a BOM for 100 bicycles might show:

- 100 frames
- 200 wheels
- 400 tires
- 8000 spokes
- ...

### 3. BOM Implosion

BOM implosion is the reverse process, showing all the finished products that use a particular component. It's valuable for assessing the impact of component changes or shortages.

Example:
Imploding the BOM for a specific type of brake might show it's used in:

- Mountain Bike Model A
- City Bike Model B
- Electric Bike Model C

### 4. Where-Used Analysis

This shows all the places where a specific component is used across different products or sub-assemblies.

Example:
A particular ball bearing might be used in:

- Front wheel hub
- Rear wheel hub
- Pedal assembly
- Steering assembly

## BOM in Manufacturing

In manufacturing, BOMs are essential for:

1. **Material Requirements Planning (MRP)**: Determining what materials are needed, when, and in what quantities.
2. **Production Scheduling**: Planning the sequence of manufacturing operations.
3. **Inventory Management**: Tracking stock levels and planning purchases.
4. **Cost Estimation**: Calculating product costs and managing profitability.
5. **Quality Control**: Ensuring all required components are present and meet specifications.

Understanding these BOM concepts is crucial for developing an effective BOM Management System that can handle the complexities of modern manufacturing environments.
