# 🚀 RISC-V Reference SoC Tapeout Program 
<div align="center">

[![RISC-V](https://img.shields.io/badge/RISC--V-Tapeout-blue?style=for-the-badge&logo=riscv)](https://riscv.org/)
[![VSD](https://img.shields.io/badge/VSD-Program-orange?style=for-the-badge)](https://vsdiat.vlsisystemdesign.com/)

</div>

Welcome to my repository for the **Week 0 of the RISC-V Reference SoC Tapeout Program by VSD**.  
This repo documents **Week 0 Introduction and Setup**, covering *introduction to the chip design flow — from modeling to tapeout* and *setting up environment and installing required tools*.  

---

## 📅 Week 0  

### 📝 Task 1 — Video Summary  
*Summary*  

---

### ⚙️ Task 2 — Setup & Tools Installation  

#### **1. System and Virtual Machine Configuration**

To ensure optimal performance, configure a **Virtual Machine (VM)** with the following specifications:

<div align="center">

| **Specification**     | **Details**       |
|-----------------------|-------------------------|
| **Operating System**  | Ubuntu 20.04+           |
| **RAM**               | 6GB                     |
| **Storage**           | 50GB HDD                |
| **vCPUs**             | 4                       |

</div>

---

#### **2.1 Open-Source EDA Tools Installation**  

Now install the following tools:  

---

##### 🧠 Yosys – RTL Synthesis Tool  
*Yosys converts Verilog RTL designs into gate-level netlists for synthesis and optimization.*  

```bash
# Install dependencies
sudo apt-get install build-essential clang bison flex \
    libreadline-dev gawk tcl-dev libffi-dev git \
    graphviz xdot pkg-config python3 libboost-system-dev \
    libboost-python-dev libboost-filesystem-dev zlib1g-dev

# Clone and build Yosys
git clone https://github.com/YosysHQ/yosys.git
cd yosys
make
sudo make install
```

📷 *Installation successful*  
![Yosys Installed](Week0/assets/yosys_installed.png)  

✅ **Yosys Successfully Installed**  

---

##### 📟 Icarus Verilog (Iverilog) – Verilog Simulator  
*Icarus Verilog compiles and simulates Verilog designs for functional verification.*  

```bash
sudo apt-get install iverilog
```

📷 *Installation successful*  
![Iverilog Installed](Week0/assets/iverilog_installed.png)  

✅ **Iverilog Successfully Installed**  

---

##### 📊 GTKWave – Waveform Viewer  
*GTKWave is used to visualize simulation waveforms for debugging digital circuits.*  

```bash
sudo apt update
sudo apt install gtkwave
```

📷 *Installation successful*  
![GTKWave Installed](Week0/assets/gtkwave_installed.png)  

✅ **GTKWave Successfully Installed**  

---

##### Ngspice – Circuit Simulator  
*Ngspice performs analog and mixed-signal circuit simulations.*  

```bash
sudo apt update
sudo apt install ngspice
```

📷 *Installation successful*  
![Ngspice Installed](Week0/assets/ngspice_installed.png)  

✅ **Ngspice Successfully Installed**  

---

##### Magic VLSI – Layout Editor  
*Magic VLSI is an open-source tool for creating and analyzing VLSI layouts with DRC support.*  

```bash
# Install dependencies
sudo apt-get install m4 tcsh csh libx11-dev tcl-dev tk-dev \
    libcairo2-dev mesa-common-dev libglu1-mesa-dev libncurses-dev

# Clone Magic
git clone https://github.com/RTimothyEdwards/magic
cd magic

# Configure, build, and install
./configure
make
sudo make install
```

📷 *Installation successful*  
![Magic VLSI Installed](Week0/assets/magic_vlsi_installed.png)  

✅ **Magic VLSI Successfully Installed**  

---

#### **2.2 OpenLane Installation (with Docker)**  

*OpenLane is an automated flow for RTL-to-GDSII, using synthesis, placement, routing, and physical verification.*  

##### 🐳 Docker Installation  
*Docker provides a containerized environment to run OpenLane consistently.*  

```bash
# Set up Docker repository
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add Docker repository
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo \"$VERSION_CODENAME\") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# Install Docker
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Verify Docker:  
```bash
sudo docker run hello-world
```

📷 *Installation successful*  
![Docker Installed](Week0/assets/docker_installed.png)  

✅ **Docker Successfully Installed**  

---

##### OpenLane Installation  
*OpenLane integrates multiple open-source tools (like Yosys, OpenROAD, Magic, Netgen) into a single automated flow.*  

```bash
cd $HOME
git clone https://github.com/The-OpenROAD-Project/OpenLane
cd OpenLane
make
make test
```

📷 *Installation successful*  
![OpenLane Installed](Week0/assets/openlane_installed.png)  

✅ **OpenLane Successfully Installed**  

---

### 🌟 Key Learnings from Week 0  
- Installed and verified **open-source EDA tools**.  
- Set up **Docker + OpenLane**.  
- Learned about the chip design pipeline from **modeling to tapeout**.  

---

## 🙏 Acknowledgment  

I am thankful to the entire VSD Team and the program partners for this incredible learning opportunity.  

---
