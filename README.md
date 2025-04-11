# Verilog-Analysis-with-AI

Welcome to the **Verilog Analysis with AI** project! This repository contains a Python script that analyzes Verilog hardware description language (HDL) files using a small language model (TinyLlama-1.1B) and tools like Verilator and Icarus Verilog. The goal is to automate the review and improvement of Verilog code, making it useful for students, researchers, and engineers new to HDL design.

## Table of Contents
- [Why This Project?](#why-this-project)
- [How It Works](#how-it-works)
- [Installation](#installation)
- [Usage](#usage)
- [When to Use](#when-to-use)
- [Challenges Faced](#challenges-faced)
- [Why This Method? Why Not Others?](#why-this-method-why-not-others)
- [Future Improvements](#future-improvements)
- [Research Context](#research-context)
- [Presentation Guide](#presentation-guide)
- [Contributing](#contributing)
- [License](#license)

## Why This Project?
Verilog is a complex language used to design digital circuits, but manually reviewing code for errors or optimizing it can be time-consuming and error-prone, especially for beginners. This project uses artificial intelligence (AI) to:
- Detect syntax errors and suggest improvements.
- Provide benchmarks (e.g., lines of code, runtime).
- Simulate Verilog designs to verify functionality.
- Help students like me, who had no prior knowledge, learn and present HDL analysis.

I started this because I needed to analyze 8025 Verilog files for a college assignment, and manual review was impossible. AI offered a scalable solution, inspired by research into automated code analysis.

## How It Works
The script does the following:
1. **Scans Files**: Finds Verilog files in a Google Drive folder (excluding testbenches).
2. **Linting**: Uses Verilator to check for syntax errors.
3. **Simulation**: Runs Icarus Verilog to simulate the design and generate output.
4. **AI Analysis**: Uses TinyLlama-1.1B (a small language model) to summarize correctness and suggest improvements.
5. **Output**: Saves results to an Excel file with design specs, full Verilog code, benchmarks, and AI insights.

The process is automated in Google Colab, leveraging its free GPU for AI processing.

## Installation
To run this project, you need Python, Google Colab, and some dependencies. Follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/Verilog-Analysis-with-AI.git
   cd Verilog-Analysis-with-AI
## 
## Installing Required Software
```bash
!pip install transformers pandas openpyxl numpy bitsandbytes accelerate
!apt-get update
!apt-get install -y verilator iverilog
```
1. **Transformers** :: For loading the Phi-3.5-mini-instruct model (AI analysis).  
2.**pandas**: For creating and saving the Excel output.  
3.**openpyxl**: For writing to Excel files. 
4.**numpy**: For numerical operations (e.g., token handling). 
5.**bitsandbytes**: For 4-bit quantization to manage memory.  
6.**accelerate**: Optimizes model loading (though not fully utilized here).  
