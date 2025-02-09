#  HCL-LTP-Testing  

## Project Overview  
This project focuses on **Linux Test Project (LTP)** for kernel validation and performance benchmarking. As part of my **HCL Internship**, I executed LTP tests on a **baseline kernel**, analyzed logs, and identified critical parameters like **I/O performance, file system performance, and memory management**.  

## **Objectives**  
- Install and configure **LTP (Linux Test Project)**  
- Run **kernel tests** and analyze logs  
- Identify **critical performance parameters**  
- Compare **baseline vs. modified kernel**  


## ⚙️ **LTP Installation & Setup**  
### 1️⃣ **Install Dependencies**  

sudo apt update
sudo apt install -y git build-essential autotools-dev automake

2️⃣ Clone LTP Repository

git clone https://github.com/linux-test-project/ltp.git
cd ltp

3️⃣ Build and Install LTP

make autotools
./configure
make -j$(nproc)
sudo make install

4️⃣ Verify Installation

ltp/runltp -h

If the help menu appears, LTP is successfully installed! 

🏁 Running LTP Test Cases
Run All Test Cases - sudo ./runltp

Run Specific Test (e.g., File System) - sudo ./runltp -f fs

Run Memory Management Tests - sudo ./runltp -f mm

Save Test Logs - sudo ./runltp | tee ltp_test_log.txt
