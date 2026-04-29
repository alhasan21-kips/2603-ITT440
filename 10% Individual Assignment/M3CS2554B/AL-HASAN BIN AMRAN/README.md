# AL-HASAN BIN AMRAN

# 🖼️ Batch Image Processing System (Concurrent & Parallel Programming)

## 📌 Overview
This project demonstrates the implementation of **sequential**, **concurrent (multithreading)**, and **parallel (multiprocessing)** approaches in Python using a **Batch Image Processing System**.

The system processes a large number of images and compares execution performance between different programming models.

---

## 🎯 Objectives
- Process a large volume of images automatically
- Implement:
  - Sequential processing
  - Concurrent processing (threading)
  - Parallel processing (multiprocessing)
- Measure and compare execution time
- Visualize performance using a graph
- Provide a GUI for user interaction

---

## 🛠️ Technologies Used
- Python 3.x
- Tkinter (GUI)
- Pillow (Image Processing)
- multiprocessing (Parallel Programming)
- concurrent.futures (Threading)
- matplotlib (Graph Visualization)

---

## ⚙️ Features
- 📁 Select input and output folders
- 🧪 Auto-generate large number of images
- ⚡ Three processing methods:
  - Sequential
  - Threading
  - Multiprocessing
- 🧠 CPU core detection
- ⏱️ Execution time measurement
- 📊 Performance graph visualization
- 🖥️ Responsive GUI (non-freezing)

---

## 🧩 System Design

### 🔹 Workflow
1. User selects input & output folder
2. User generates images (optional)
3. System processes images using:
   - Sequential method
   - Threading method
   - Multiprocessing method
4. Execution time is recorded
5. Graph is displayed for comparison

---

## 🧠 Concepts Applied

### 1. Sequential Processing
Processes images one by one:
```python
for img in images:
    process(img)
````

---

### 2. Concurrent Programming (Threading)

Uses threads for I/O-bound tasks:

```python
from concurrent.futures import ThreadPoolExecutor
```

* Improves performance for file operations
* Limited by Python GIL

---

### 3. Parallel Programming (Multiprocessing)

Uses multiple CPU cores:

```python
from multiprocessing import Pool
```

* True parallel execution
* Best performance for CPU-intensive tasks

---

## ⏱️ Performance Measurement

Execution time is measured using:

```python
start = time.time()
# process
end = time.time()
```

---

## 📊 Sample Output

```
CPU Cores Used: 8

Processing 1000 images...

===== PERFORMANCE RESULT =====
Sequential Processing      : 25.40 seconds
Threading (Concurrent)    : 18.20 seconds
Multiprocessing (Parallel): 9.75 seconds
```

---

## 📈 Performance Graph

A bar chart is generated using matplotlib to compare execution times:

* X-axis → Processing method
* Y-axis → Time (seconds)

---

## 🖥️ GUI Implementation

The system uses Tkinter to provide:

* Folder selection
* Image generation
* Start processing button
* Result display

---

## ⚠️ Challenges & Solutions

### ❌ GUI Freezing

**Problem:** GUI becomes unresponsive during processing
**Solution:** Use threading to run tasks in background

```python
threading.Thread(target=start_processing).start()
```

---

### ❌ Duplicate GUI Windows

**Problem:** Multiprocessing creates multiple GUI windows
**Solution:**

```python
if __name__ == "__main__":
```

---

### ❌ Matplotlib Warning

**Problem:**

```
Starting a Matplotlib GUI outside of the main thread
```

**Solution:**

```python
root.after(0, lambda: show_graph(...))
```

---

### ❌ Image Overwriting

**Problem:** Generated images overwrite existing ones
**Solution:** Continue numbering filenames

---

## 📂 Project Structure

```
project/
│
├── input_images/
├── output_images/
├── main.py
└── README.md
```

---

## 🚀 How to Run

### 1. Install dependencies

```bash
pip install pillow matplotlib
```

---

### 2. Run program

```bash
python main.py
```

---

### 3. Steps

1. Select input folder
2. Generate images (optional)
3. Select output folder
4. Click "Start Processing"

---

## 📌 Notes

* Recommended image count: **1000–5000**
* Avoid extremely large numbers (e.g. 1,000,000+) due to system limitations
* Multiprocessing gives best performance

---

## 🧠 Conclusion

* Sequential processing is the slowest
* Threading improves performance for I/O tasks
* Multiprocessing is the fastest due to multi-core utilization

