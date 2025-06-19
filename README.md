Fuzzy Logic Thermal Control System Simulation
https://screenshot.png

Overview
This PyGame application simulates a fuzzy logic-based thermal control system that maintains a target temperature while accounting for ambient environmental influences. The system uses fuzzy logic rules to determine heating, cooling, or neutral actions based on the temperature error (difference between current and target temperature) and the rate of error change.

Features
Real-time Temperature Simulation: Visualizes temperature changes over time

Fuzzy Logic Controller: Uses error and error rate to determine control actions

Interactive Controls:

Start/Pause simulation

Reset to initial state

Adjust target temperature

Toggle between summer/winter ambient modes

Comprehensive Visualization:

Temperature history graph

Thermometer display with color-coded temperature ranges

System metrics panel showing error, error rate, and action strength

Responsive Design: Clean UI with intuitive controls

How It Works
The system uses a fuzzy logic controller with triangular and trapezoidal membership functions to determine the appropriate control action:

Fuzzification: Converts crisp input values (error and error rate) into fuzzy sets

Rule Evaluation: Applies predefined rules to determine appropriate actions

Defuzzification: Converts fuzzy output into a crisp control value

The controller outputs HEAT, COOL, or NEUTRAL actions with varying strengths based on the system's state. Ambient temperature acts as a constant influence that the controller must counteract to maintain the target temperature.

Installation
Ensure you have Python 3.7+ installed

Install required dependencies:

bash
pip install pygame
Download the simulation file:

bash
git clone https://github.com/yourusername/fuzzy-thermal-control.git
cd fuzzy-thermal-control
Run the simulation:

bash
python fuzzy_thermal_control.py
Usage
Start/Pause: Toggle simulation running state

Reset: Return to initial conditions

Target Temperature: Use +/- buttons to adjust target

Ambient Mode: Toggle between Summer (30°C) and Winter (10°C) modes

Metrics Panel: View real-time system metrics including error and action strength

Technical Details
Fuzzy Membership Functions:

Triangular: triangular_mf(x, a, b, c)

Trapezoidal: trapezoidal_mf(x, a, b, c, d)

Control Rules:

python
rules = [
    {'condition': min(err_neg, err_dot_neg), 'action': 'COOL', 'strength': -1.0},
    {'condition': min(err_neg, err_dot_zer), 'action': 'COOL', 'strength': -0.8},
    # ... additional rules
]
Simulation Parameters:

Time step: 0.5 seconds

Control multiplier: 0.6 (base), 1.2 (near target)

Ambient influence factor: 0.005

License
This project is licensed under the MIT License. See the LICENSE file for details.