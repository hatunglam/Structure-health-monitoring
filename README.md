# Data Driven Structural Health Monitoring

## Background

Engineering infrastructure such as chemical plants, aircraft, or nuclear power stations are very expensive and safety-critical. To ensure safe operation, they are periodically inspected using non-destructive testing techniques such as ultrasound inspection. This process, while vital, is costly and carried out relatively infrequently. An alternative is to monitor the state of a structure at all times using permanently installed sensors.

One highly promising technology for this is to make **ultrasonic guided wave measurements** using such a network of attached sensors. High-frequency sound from installed sensors propagates in all directions to monitor components from a small number of locations. If multiple pairs of sensors are used, then the state of a structure may be imaged using standard focusing algorithms.

In theory, this is straightforward; however, the sound reflects from all features in the structure. The resulting recorded time responses are therefore complicated by echoes from all geometry. 

In an ideal scenario, the complexity of the signals may be suppressed by subtracting reference data captured earlier when the structure is in a known condition. If the structure remains unchanged, subtraction will show no difference. If damage has appeared, it will remain after subtraction of the reference data, as illustrated in **Figure 1b**.

In real conditions, factors such as temperature, load, and humidity can have dramatic effects on this subtraction process, reducing the ability to suppress background features and reveal damage. This mini-project aims to address this challenge using **data-driven approaches** to improve the performance of subtraction-based methods.

---

## Project Description

A **water tank** behind the Queens Building was instrumented with a network of **9 ultrasonic sensors** in 2012. An automated data acquisition system recorded signals roughly every 15 minutes for 10 years. Although there were interruptions due to equipment failures and refurbishments, this produced a large dataset.

The overall aim is to use this data to **develop data-driven methods** to improve the subtraction process in ultrasonic guided wave SHM. Several approaches are proposed, as outlined below.

### Potential Approaches

1. **Sensor Pair Basis:**  
   Analyze data on a per-sensor-pair basis to suppress structural features in ultrasonic responses.  
   Each pair is treated independently.

2. **Image Basis:**  
   Convert data from each sensor pair into structural images and develop processing methods to improve reference subtraction and suppress non-defect features.

3. **Hybrid Approach:**  
   Combine the above two methods to leverage their respective advantages.

Each method can offer efficient solutions with specific trade-offs. A brute-force approach based on baseline fitting is discussed in [2], while more recent **machine learning methods** ([3], [4]) have shown promising results in improving subtraction robustness.

---

## Data

Data is provided for **four sensor pairs** from this structure over the full experiment duration, including measurements with induced damage. A setup description file (sensor locations, conditions, etc.) is also provided.  

This dataset is sufficient to:
- Produce **images of the structure**, or
- Demonstrate the **robustness** of developed subtraction/improvement techniques across multiple sensor pairs.

---

## Initial Work Plan

Suggested core tasks include:

1. **Familiarization** with the problem and current state of the art.  
2. **Demonstration of defect detection** through subtraction in a simple case.  
3. **Image generation** of the structural condition from recorded data.  
4. **Selection of a data-driven approach** to improve subtraction performance.  
5. **Performance evaluation** of the proposed method.  
6. **Extension** to test generalizability and transferability to other systems.

> This is a suggested outline — the exact research path is at the student’s discretion.

---
