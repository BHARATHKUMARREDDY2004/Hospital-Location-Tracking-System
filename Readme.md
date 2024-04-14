## Dataset based on UWB for Clinical Establishments

### Introduction
This dataset, donated on 11/21/2022, presents a unique collection of data obtained from an intelligent surveillance system implemented in clinical establishments. The system leverages Ultra Wide Band (UWB) technology to track and monitor patient movements within hospitals. With the aim of enhancing patient management and optimizing healthcare delivery, this dataset provides valuable insights into the chronophagous behavior of patients as they move in and out of hospital premises.

#### Purpose
The primary purpose of this dataset is to support research and development in the field of smart healthcare systems. By utilizing UWB technology, the dataset offers opportunities for exploring innovative approaches to patient tracking, monitoring, and management within clinical environments.

#### Funding
The creation of this dataset was made possible through funding provided by the Department of Science and Technology-Natural Resource Database Management System (DST-NRDMS) [Grant No: NRDMS/UG/NetworkProject/e-13/2019 (C) P-4]. This support underscores the importance of advancing technology-driven solutions for healthcare management.

### Dataset Overview
- **Instances**: 608
- **Features**: 8
- **Feature Types**: Integer and Categorical
- **Missing Values**: None
- **License**: Creative Commons Attribution 4.0 International (CC BY 4.0)

**Primary Objective:**

The primary objective of the Ultra Wide Band (UWB) system is to determine the precise location of a signal transmitter, "TAB00001", within the monitored area using triangulation techniques. By leveraging the signals received by multiple anchors, namely "ANCH0001", "ANCH0002", and "ANCH0003", the system aims to calculate the position coordinates of the transmitter.

**Triangulation Technique:**

1. **Signal Transmission:** The transmitter, "TAB00001", emits signals that are received by multiple anchors placed in known locations within the area.

2. **Time of Arrival (ToA) Measurement:** Each anchor measures the time it takes for the signal emitted by the transmitter to arrive. This time difference, along with the known speed of signal propagation (usually the speed of light), helps in calculating the distances between the transmitter and each anchor.

3. **Distance Calculation:** Using the ToA measurements and the speed of signal propagation, the distances between the transmitter and each anchor can be calculated using the formula:
      - Distance = speed of light * time diffrence

4. **Triangulation:** With the distances from the transmitter to each anchor known, triangulation techniques are employed to determine the transmitter's position. Three anchors are sufficient for triangulation, as they provide three distance measurements.

   - One common method is the **Trilateration** technique, where circles (or spheres in 3D) are drawn around each anchor with a radius equal to the calculated distance. The intersection points of these circles (or spheres) represent the possible locations of the transmitter. 

      - Euclidean distance : $\sqrt{(x'-x)^2 + (y'-y)^2}$

   - Another method is the **Multilateration** technique, which uses hyperbolic curves instead of circles. The transmitter's position is determined by finding the intersection points of these hyperbolic curves.

Equate Distance and Euclidean distance, find the coordinate.

**Triangulation Method:**

The provided code segment implements a triangulation method to estimate the position of a transmitter using distance measurements from three anchors ("ANCH0001", "ANCH0002", and "ANCH0003"). 

1. **Distance Calculation:** The distances between the transmitter and each anchor are calculated using time-of-flight measurements and the speed of light.

2. **Equation Setup:** For each pair of anchors, a system of equations representing the intersection of circles (or spheres) centered at each anchor and with radii equal to the measured distances is set up.

3. **Numerical Solution:** The equations are solved numerically using the `fsolve` function from `scipy.optimize` to find the intersection points, which represent potential positions of the transmitter.

4. **Selection of Valid Coordinates:** The coordinates of the potential positions are evaluated, and the valid coordinate that lies in the positive quadrant (where both x and y coordinates are positive) is selected.

By repeating this process for each sequence of distance measurements, the code estimates the transmitter's position through triangulation.

**Synthetic Data Interpolation:**

Generating synthetic data points to simulate another area in the hospital, specifically the patient ward. 

1. **Random Coordinate Generation:** Within a loop iterating 342 times, random x and y coordinates are generated using the `random.randint` function. The range for x coordinates is set between 5 and 8, while for y coordinates, it is set between 3 and 8.

2. **Data Format:** Each generated coordinate is appended to the `coordinates` list in the format [x, y, 1], where the third element represents the patient ward area.

This process interpolates synthetic data to mimic the distribution of coordinates in the patient ward area, aiding in the analysis and testing of algorithms or systems designed for that specific hospital section.

- **Data Structure:** The dataset comprises 684 entries and 3 columns.
- **Feature Description:**
  1. **x:** Represents the x-coordinate of the data points. It is stored as a floating-point number.
  2. **y:** Represents the y-coordinate of the data points. It is stored as a floating-point number.
  3. **Room:** Indicates the designation of the area corresponding to the coordinates, possibly representing different sections or rooms within the hospital. It is stored as an integer.

This dataset provides spatial information about various locations within the hospital, facilitating analysis and visualization of the distribution of coordinates across different areas.

## Result Analysis
You can go through the documentation of this project.

## Contributing
Contributions are welcome! Feel free to submit pull requests or open issues for any improvements or suggestions.
