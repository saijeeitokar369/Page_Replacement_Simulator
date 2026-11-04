# 💻 Page Replacement Simulator
### Operating Systems | Memory Management | Python

<p align="center">
  **A Python-based simulation and comparative analysis of FIFO, LRU and Optimal Page Replacement Algorithms.**
</p>

---

## 📌 About the Project

The **Page Replacement Simulator** is an Operating Systems project developed to understand and demonstrate how different page replacement algorithms manage memory when a page fault occurs.

When physical memory is full and a new page needs to be loaded, the operating system must decide which existing page should be replaced. This project simulates three widely used page replacement algorithms:

- **FIFO (First In First Out)**
- **LRU (Least Recently Used)**
- **Optimal Page Replacement**

The simulator tracks page hits, page faults, frame contents and hit/fault ratios to compare the performance of these algorithms.

## 🎯 Project Objectives

- Understand the concept of virtual memory and page replacement.
- Implement FIFO, LRU and Optimal algorithms using Python.
- Identify page hits and page faults.
- Perform step-by-step manual tracing.
- Study Belady's Anomaly.
- Compare algorithm performance using different reference strings and frame sizes.

## ⚙️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Algorithm implementation |
| Google Colab | Coding and execution |
| Jupyter Notebook | Simulation and analysis |
| GitHub | Project documentation and version control |

**Python Libraries:**
- `collections.deque` – Queue-based frame management.
- Standard Python functions – Simulation, calculations and output formatting.

## 🧠 Algorithms Implemented

### 1. FIFO – First In First Out

FIFO replaces the page that entered memory first.

- Follows the Queue (FIFO) principle.
- Maintains pages in their arrival order.
- Replaces the oldest page when memory is full.
- Does not consider how frequently or recently a page is used.

### 2. LRU – Least Recently Used

LRU replaces the page that has not been used for the longest period of time.

- Tracks recent page usage.
- Updates page order whenever a page is accessed.
- Removes the least recently used page when memory is full.
- Generally performs better than FIFO on some reference strings.

### 3. Optimal Page Replacement

Optimal replaces the page whose next use is farthest in the future.

- Examines upcoming page references.
- Replaces the page that will be needed last.
- Produces the minimum possible page faults for a given reference string and frame count.
- Requires future reference knowledge, making exact implementation impractical in a real operating system.

## ✨ Key Features

- Implementation of three page replacement algorithms.
- Configurable reference strings.
- Adjustable number of memory frames.
- Step-by-step frame status display.
- Automatic page hit and page fault counting.
- Hit ratio and fault ratio calculation.
- Manual tracing and verification.
- Belady's Anomaly experiment.
- Comparative performance analysis.

## 📊 Part A: Algorithm Simulation

**Default Reference String:**

`1, 2, 3, 1, 4, 2, 5`

**Number of Frames:** 3

The simulator processes each page reference and displays the frame contents along with its result (Hit or Fault).

### Performance Comparison

| Algorithm | Page Faults | Page Hits |
|---|---:|---:|
| FIFO | 5 | 2 |
| LRU | 5 | 2 |
| Optimal | 5 | 2 |

*Note: These results correspond to the default seven-page reference string in the notebook.*

## 📝 Part B: Manual Tracing

**Aim:** To manually trace and analyze FIFO, LRU and Optimal Page Replacement Algorithms using a given reference string and three memory frames.

**Given Input:**

- Reference String: `7, 0, 1, 2, 0, 3, 0, 4, 2, 3, 0, 3, 2`
- Number of Frames: 3
- Total Page References: 13

### Manual Tracing Results

| Algorithm | Page Faults | Page Hits |
|---|---:|---:|
| FIFO | 10 | 3 |
| LRU | 9 | 4 |
| Optimal | 7 | 6 |

### Performance Analysis

| Algorithm | Hit Ratio | Fault Ratio |
|---|---:|---:|
| FIFO | 23.08% | 76.92% |
| LRU | 30.77% | 69.23% |
| Optimal | 46.15% | 53.85% |

**Observation:** Optimal Page Replacement performs best for this reference string because it produces the minimum number of page faults.

## 🔬 Part C: Experiments and Analysis

### Experiment 1: Belady's Anomaly

**Aim:** To study the effect of increasing the number of memory frames on page faults.

**Reference String:**

`1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5`

The experiment is performed using three frames and four frames.

| Algorithm | Faults (3 Frames) | Faults (4 Frames) |
|---|---:|---:|
| FIFO | 9 | 10 |
| LRU | 10 | 8 |
| Optimal | 7 | 6 |

**Observation:**

FIFO produces more page faults when the number of frames increases from three to four.

This phenomenon is known as **Belady's Anomaly**.

LRU and Optimal do not exhibit this anomaly because they satisfy the stack property under the standard page replacement model.

### Experiment 2: Own Reference Strings

The project also explores custom page reference strings to compare FIFO and LRU performance.

Two cases are considered:

1. Reference strings where LRU performs better than FIFO.
2. Reference strings where FIFO performs better than or equal to LRU.

The results are verified through the simulator.

## 📐 Important Formulas

**Hit Ratio:**

`Hit Ratio = (Page Hits / Total Page References) × 100`

**Fault Ratio:**

`Fault Ratio = (Page Faults / Total Page References) × 100`

**Total Page References:**

`Page Hits + Page Faults`

## 🚀 How to Run the Project

**Option 1: Google Colab**

1. Download `Page_Replacement_Simulator.ipynb`.
2. Open [Google Colab](https://colab.research.google.com/).
3. Upload the downloaded notebook.
4. Run all code cells.
5. Observe the output and compare the algorithms.

**Option 2: Jupyter Notebook**

1. Clone the repository:

   ```bash
   git clone https://github.com/saijeeitokar369/Page_Replacement_Simulator.git
   ```

2. Open the project folder:

   ```bash
   cd Page_Replacement_Simulator
   ```

3. Install Jupyter Notebook if required:

   ```bash
   pip install notebook
   ```

4. Launch Jupyter:

   ```bash
   jupyter notebook
   ```

5. Open `Page_Replacement_Simulator.ipynb` and run the cells.

## 📂 Project Structure

```text
Page_Replacement_Simulator/
│
├── Page_Replacement_Simulator.ipynb
│
├── Manual_Tracing.pdf
│
├── Experiment_And_Analysis.pdf
│
└── README.md
```

## 📚 Learning Outcomes

Through this project, I explored:

- Memory management concepts in operating systems.
- Page faults and page hits.
- Implementation of queue-based and recency-based algorithms.
- Future-reference analysis in Optimal Page Replacement.
- Manual tracing and algorithm verification.
- Comparative analysis and Belady's Anomaly.

## 🏁 Conclusion

This project demonstrates how different page replacement algorithms manage memory and affect system performance.

The experiments show that FIFO can suffer from Belady's Anomaly, LRU considers recent page usage, and Optimal provides the minimum possible page faults when future references are known.

Overall, this project strengthened my understanding of Operating System memory management through practical implementation, experimentation and analysis.

---

## 📎 Project Resources

- 📓 [Python Simulation Notebook](Page_Replacement_Simulator.ipynb)
- 📄 [Manual Tracing Documentation](Manual_Tracing.pdf)
- 📊 [Experiments and Analysis](Experiment_And_Analysis.pdf)

## 👩‍💻 Author

**Saijee Itokar**

B.Tech – Data Analytics  
SAGE University, Bhopal

🔗 **GitHub:** [saijeeitokar369](https://github.com/saijeeitokar369)

---

⭐ If you find this project useful, feel free to explore the repository and its implementations.

*Developed as part of an Operating Systems practical project.*
