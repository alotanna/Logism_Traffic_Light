# Traffic Light Controller for Four-Way Intersection

A digital logic implementation of an intelligent traffic light control system for a four-way intersection using state machine design with D-flip flops.

## 🚦 Overview

This project implements a traffic light controller that manages traffic flow at a four-way intersection using a finite state machine approach. The system uses two D-flip flops to create four distinct states, each controlling the traffic light patterns for North-South and East-West directions.

## 📋 Features

- **4-State Traffic Control**: Manages complete traffic light cycle for both directions
- **Timing-Based Transitions**: Uses 5-second and 15-second timing intervals
- **Safe Traffic Flow**: Ensures proper yellow light transitions and prevents conflicts
- **Digital Logic Implementation**: Built using D-flip flops and combinational logic

## 🔧 System Architecture

### State Machine Design

The controller uses **2 D-flip flops (A, B)** to create 4 states:

| State | A | B | North-South | East-West |
|-------|---|---|-------------|-----------|
| 00    | 0 | 0 | 🟢 Green    | 🔴 Red    |
| 01    | 0 | 1 | 🟡 Yellow   | 🔴 Red    |
| 10    | 1 | 0 | 🔴 Red      | 🟢 Green  |
| 11    | 1 | 1 | 🔴 Red      | 🟡 Yellow |

### Timing Control

The system uses two timing inputs:
- **x = 1**: When counter reaches 5 seconds (for yellow light duration)
- **y = 1**: When counter reaches 15 seconds (for green light duration)

### State Transition Logic

The next state logic is implemented using the following truth table:

| Current State | Timing | Next State |
|---------------|--------|------------|
| A B           | x y    | A(t+1) B(t+1) |
| 0 0           | 0 0    | 0 0        |
| 0 0           | 0 1    | 0 1        |
| 0 0           | 1 0    | 0 0        |
| 0 0           | 1 1    | X X        |
| 0 1           | 0 0    | 0 1        |
| 0 1           | 0 1    | 0 1        |
| 0 1           | 1 0    | 1 0        |
| 0 1           | 1 1    | X X        |
| 1 0           | 0 0    | 1 0        |
| 1 0           | 0 1    | 1 1        |
| 1 0           | 1 0    | 1 0        |
| 1 0           | 1 1    | X X        |
| 1 1           | 0 0    | 1 1        |
| 1 1           | 0 1    | 1 1        |
| 1 1           | 1 0    | 0 0        |
| 1 1           | 1 1    | X X        |

*Note: X represents don't care conditions*

## 🚀 Implementation

### Hardware Requirements
- 2 × D-flip flops
- Combinational logic gates (AND, OR, NOT)
- Timing counter circuit
- LED indicators for traffic lights

### Software Tools
- Digital logic simulator (e.g., Logisim)

## 📊 Operation Cycle

1. **State 00**: North-South GREEN (15 seconds) → East-West RED
2. **State 01**: North-South YELLOW (5 seconds) → East-West RED
3. **State 10**: North-South RED → East-West GREEN (15 seconds)
4. **State 11**: North-South RED → East-West YELLOW (5 seconds)
5. **Repeat**: Returns to State 00

## 🔬 Design Methodology

This project demonstrates:
- **Finite State Machine Design**: Systematic approach to sequential logic
- **State Encoding**: Efficient use of flip-flops for state representation
- **Timing Constraints**: Real-world timing requirements integration
- **Safety Considerations**: Proper traffic light sequencing

## 🧪 Testing

The design includes comprehensive testing scenarios:
- State transition verification
- Timing constraint validation
- Edge case handling
- Safety requirement compliance

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests for:
- Design optimizations
- Additional timing modes
- Enhanced safety features
- Documentation improvements

## 🎓 Educational Context

This project is designed for digital logic and computer engineering coursework, demonstrating practical applications of:
- Sequential logic design
- State machine implementation
- Real-world timing constraints
- Safety-critical system design

## 📞 Contact

For questions or suggestions regarding this traffic light controller implementation, please contact me at: austine.iheji@ashesi.edu.gh.

---

*This project demonstrates the practical application of digital logic principles in traffic management systems, emphasizing both technical implementation and safety considerations.*
