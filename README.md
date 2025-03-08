```markdown
# CNC Milling Performance Analysis & Fault Detection

This Streamlit application analyzes CNC milling performance and detects faults using a deep learning model.

## Features
- Upload sensor data for analysis.
- Predict CNC milling performance using an LSTM model.
- Uses feature scaling for accurate predictions.
- User-friendly interface with a navigation sidebar.

## Installation

### **1. Clone the Repository**
```sh
git clone https://github.com/flubber-lab/CNC_Performance_Analysis.git
cd cnc-analysis
```

### **2. Set Up a Virtual Environment**
```sh
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### **3. Install Dependencies**
```sh
pip install -r requirements.txt
```

### **4. Run the Streamlit App**
```sh
streamlit run streamlit_app.py
```

## Deployment on AWS EC2

### **1. Launch an EC2 Instance**
- Use **Ubuntu 22.04** or any preferred Linux distribution.
- Allow inbound traffic on **port 8501** (for Streamlit).
- Connect to the instance via SSH.

### **2. Install Dependencies on EC2**
```sh
sudo apt update && sudo apt upgrade -y
sudo apt install python3-pip python3-venv -y
```

### **3. Clone the Repository**
```sh
git clone https://github.com/flubber-lab/CNC_Performance_Analysis.git
cd cnc-analysis
```

### **4. Set Up a Virtual Environment**
```sh
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### **5. Run the Streamlit App on EC2**
```sh
streamlit run streamlit_app.py --server.port 8501 --server.address 0.0.0.0
```

### **6. Access the App**
- Find your **EC2 Public IP** from the AWS Console.
- Open a browser and go to:
  ```
  http://<your-ec2-public-ip>:8501
  ```

### **7. Run the App in the Background (Optional)**
If you want the app to run even after closing the SSH session:
```sh
nohup streamlit run streamlit_app.py --server.port 8501 --server.address 0.0.0.0 > output.log 2>&1 &
```

## File Structure
```
/cnc-analysis
│── streamlit_app.py       # Main Streamlit app
│── cnc_model.h5           # Pre-trained LSTM model
│── requirements.txt       # Python dependencies
│── README.md              # Documentation
│── bg.jpg                 # Background image
```

## Troubleshooting
- **If Streamlit doesn’t start**, check logs:
  ```sh
  cat output.log
  ```
- **Ensure port 8501 is open** in the EC2 Security Group.
- **Check Python dependencies** with:
  ```sh
  pip list
  ```

## Author
Developed by **Arunkumar Saravanan**  
```

