# Robot UR5E: Simulation of Polishing on Sheet Metal

This simulation demonstrates the use of **force control** to perform uniform polishing on sheet metal with an irregular surface. A safety mechanism was implemented to prevent accidental impacts with the work area.

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/48b99bb1-96d9-4660-a181-b834b9884eb3" alt="Robot Polishing Simulation" />
</div>

---

## 🚨 Safety Plane
A **safety plane** was defined at a height of `( ) [mm]` along the Z-negative axis with respect to the work plane. This ensures that the robot avoids any unintended collisions with the work area.

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/158a2533-37f8-43c4-a262-b302c235caac" alt="Safety Plane" />
</div>

---

## 🔧 TOOL
A square-based parallelepiped was used to simulate the model of a polisher. The tool includes discretizations and a threaded shank at the center to allow the robot's gripper to securely grab it.

**Dimensions:**
- **Base:** 75 x 75 mm
- **Height:** 30 mm
- **Threaded Shank Height:** 40 mm

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/a59baced-c2d4-4adc-a28b-8642bd3db175" alt="Tool Design" />
</div>

---

## 🛠️ SHEET METAL
The sheet metal surface includes irregularities that the robot must polish uniformly by applying force control.

**Dimensions:**
- **Length:** 1000 mm
- **Width:** 300 mm
- **Height:** 30 mm

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/b7e72a74-4fd3-4efd-95e0-dbfdb283f0c6" alt="Sheet Metal" />
</div>

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/1d123036-108e-4f75-97e0-ab7d9df1511d" alt="Blocking Sheet Metal" />
</div>

---

## ⚖️ PROCEDURE: Force Control
To simulate polishing uniformity that closely resembles industrial applications, the **MOVE_P** command was integrated into the force control system. This command maintains a constant tool speed during polishing.

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/062763bb-d62d-4283-adc3-39a57c14ac4e" alt="Force Control Procedure" />
</div>

### 🔍 Observations:
- **Low forces (1N and 3N):** The robot reversed the direction of force application.
- **High forces (10N):** Deformation of the sheet metal occurred.

Based on these results, a **force value of 8N** was selected as the optimal balance for uniform polishing.

> **Note:** Proper management of robot singularities is critical to ensure smooth operation and avoid errors.

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/4c3ef81e-df45-4949-ade3-be7ccd949a92" alt="Observations 1" />
  <img src="https://github.com/user-attachments/assets/8a647636-29a0-4a4a-ba79-7cb62987b822" alt="Observations 2" />
</div>

---

## ⏳ LOOP END CONDITION
To properly manage the application's subprogram and allow the loop to terminate correctly, a **condition** was implemented. This condition evaluates as **TRUE** when the distance from the **START_POINT** to the acquired **REAL_TIME position** is maintained.

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/7dacbc4e-3f97-4e5c-af83-15116f1d390f" alt="Loop End Condition" />
</div>

---

## SCRIPT
<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/2564f42e-eb1b-4772-85be-1a9eca6ab51b" alt="Script" />
</div>
