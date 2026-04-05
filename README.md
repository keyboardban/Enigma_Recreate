# Enigma Machine Simulator (Python)

A pure Python implementation of the WWII Enigma Machine, focusing on object-oriented design and the mathematical logic behind the encryption process.

## Core Features
- **Rotors I - V**: Accurately modeled wiring and stepping notches.
- **Reflectors B & C**: Implemented the fixed reflection mapping.
- **Plugboard**: Custom character swapping logic (Reciprocity guaranteed).
- **Triple-Stepping Mechanism**: Includes the famous "Double-Stepping" anomaly of the original Enigma.

## Technical Implementation
The simulation treats each component as a modular object. The encryption logic follows the permutation formula:
$$E = P \cdot R_3 \cdot R_2 \cdot R_1 \cdot UKW \cdot R_1^{-1} \cdot R_2^{-1} \cdot R_3^{-1} \cdot P^{-1}$$
Where $P$ is the Plugboard, $R$ represents the Rotors, and $UKW$ is the Reflector.

## Quick Start
```python
# Example setup in the notebook/script
pb = Plugboard("AR GK OX")
rotors = [Rotor('I'), Rotor('II'), Rotor('III')]
enigma = EnigmaMachine(reflector=Reflector('B'), rotors=rotors, plugboard=pb)

print(enigma.process_text("HELLOWORLD"))
