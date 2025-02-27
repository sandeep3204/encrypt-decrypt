
# 🔒 Image-Based Message Encryption and Decryption

## **📌 Overview**
This project demonstrates a simple yet effective technique to hide and retrieve secret messages within images using **Python and OpenCV**. It utilizes **image steganography**, where message characters are embedded into pixel values, making them invisible to the naked eye. The retrieval process is **password-protected**, ensuring secure access to the hidden message.

---

## **📑 Table of Contents**
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Files](#project-files)
- [How It Works](#how-it-works)
- [Usage Guide](#usage-guide)
- [Encryption](#encryption)
- [Decryption](#decryption)
- [Expected Output](#expected-output)
- [Applications](#applications)
- [Future Enhancements](#future-enhancements)
- [Contributors](#contributors)
- [License](#license)

---

## **🛠 Prerequisites**
Before running this project, make sure you have the following installed:
- **Python (3.x)**
- **pip (Python Package Manager)**
- **OpenCV (cv2)**
- **VS Code (or any preferred IDE)**
- **Git (for version control - optional)**

---

## **📥 Installation**

### **1️⃣ Install Python**
If Python is not installed, download and install it from [Python's official website](https://www.python.org/downloads/).

### **2️⃣ Install VS Code**
If you don’t have **Visual Studio Code (VS Code)** installed, download it from [VS Code's official site](https://code.visualstudio.com/).

### **3️⃣ Set Up a Virtual Environment (Optional, Recommended)****


Run the following command to create a virtual environment:
    python -m venv venv
Activate the environment:
  On Windows:  
    bash  -- venv\Scripts\activate
  On Mac/Linux:
    bash  -- source venv/bin/activate
4️⃣ Install Required Libraries
Use the following command to install OpenCV and OS module:

    bash  --  pip install opencv-python
The OS module is built into Python, so no separate installation is required.

5️⃣ Clone This Repository (Optional)
If you want to use this project from GitHub, run:

bash  -- git clone https://github.com/your-repo-name/image-stego.git
cd image-stego

 Project Files
    The repository contains the following files:
        📦 image-stego
         ┣ 📜 README.md                  # Documentation (this file)
         ┣ 📜 encryption.py               # Python script for encrypting messages into an image
         ┣ 📜 decryption.py               # Python script for decrypting messages from an image
         ┣ 📜 sample_image.jpg            # Sample image to test the project
         ┗ 📜 requirements.txt            # List of required dependencies

  🔍 How It Works
      The script loads an image using OpenCV.
      The secret message is embedded into the RGB pixel values.
      The image is saved as an encrypted image (encryptedImage.jpg).
      The decryption process extracts the hidden message, requiring a password for access.


  🚀 Usage Guide
    Run the encryption & Decryption script:
import cv2
import os
import string

img = cv2.imread("my_pic.jpg")

msg = input("Enter secret message:")
password = input("Enter a passcode:")

d = {}
c = {}

for i in range(255):
    d[chr(i)] = i
    c[i] = chr(i)

m = 0
n = 0
z = 0

for i in range(len(msg)):
    img[n, m, z] = d[msg[i]]
    n = n + 1
    m = m + 1
    z = (z + 1) % 3

cv2.imwrite("encryptedImage.jpg", img)
os.system("start encryptedImage.jpg")

message = ""
n = 0
m = 0
z = 0

pas = input("Enter passcode for Decryption: ")
if password == pas:
    for i in range(len(msg)):
        message = message + c[img[n, m, z]]
        n = n + 1
        m = m + 1
        z = (z + 1) % 3
    print("Decryption message:", message)
else:
    print("YOU ARE NOT auth")
    
        python encryption.py
        Enter the secret message you want to hide.
        Provide a passcode for security.
        The script will process the image and save the encrypted image as encryptedImage.jpg.
    🔓 Decryption
    Run the decryption script:
        
        python decryption.py
        Enter the passcode to retrieve the message.
        If the password matches, the hidden message is displayed.
    📸 Expected Output
        Before Encryption
        Image: my_pic.jpg

    After Encryption
    The image remains visually the same, but the message is embedded.
    
    Decryption Output
  
    Enter passcode for Decryption: ****
    Decryption message: "Hello, this is a secret!"
    🔍 Applications
        Cybersecurity – Secure communication with encrypted messages.
        Digital Watermarking – Embed ownership information into images.
        Forensics – Hiding confidential data in images.
        Military & Intelligence – Secure data transmission.
    🚀 Future Enhancements
        Implementing AES/RSA encryption for added security.
        Creating a GUI-based tool for easy user interaction.
        Extending the project to video-based steganography.
    🤝 Contributors
        👤 Jillepalli Sandeep
        📌 B.Tech Mechanical Engineering, CMR College of Engineering & Technology
        📧 [pandujillepalli222@gmail.com] | 📂 https://github.com/sandeep3204
    
    📜 License
        This project is licensed under the MIT License – free to use and modify.
    
    📢 Feedback & Contributions
        If you have any suggestions or improvements, feel free to fork this project, submit a pull request, or raise an issue in the repository.
    
    
            
