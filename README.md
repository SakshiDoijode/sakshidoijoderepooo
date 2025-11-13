Real-Time Edge Detection Viewer
Android (OpenCV C++ + OpenGL ES + JNI) + Web (TypeScript)

This project implements a real-time edge-detection system using OpenCV in C++, rendered using OpenGL ES, and supported by a TypeScript-based web viewer.

✅ Features Implemented (Android + Web)
🔹 Android Application

Camera feed integration using Camera2 API + TextureView

Frame processing in C++ via JNI

Grayscale

Canny Edge Detection

Real-time rendering using OpenGL ES 2.0 textures

Smooth performance (10–15 FPS)

Toggle between raw & processed frames (Bonus)

🔹 Web Viewer (TypeScript)

Webcam capture via browser

Edge detection algorithms:

Sobel, Canny, Prewitt, Roberts, Laplacian

Optional WebAssembly-based OpenCV processor

GPU-accelerated rendering via WebGL

Viewer displays:

Processed sample frame

Basic frame stats (FPS, resolution)

📷 Screenshots 


![Android App](screenshots/android.png)
![Web Viewer](screenshots/web.png)


(Replace these with your real screenshots in the repo.)

⚙️ Setup Instructions
Android Setup (NDK + OpenCV)
Requirements

Android Studio

Android NDK (latest recommended)

OpenCV Android SDK

Physical device for testing

Steps

Install and enable NDK in Android Studio

Download and extract OpenCV-Android-SDK

Place OpenCV into:

app/src/main/cpp/opencv/


Update CMakeLists.txt to link OpenCV

Build the project and run on a device

Web Viewer Setup (TypeScript)
Install dependencies:
npm install
npm run build

Run the local server:
npm run serve


or:

python3 serve.py

Open in browser:
http://localhost:8000

🧠 Architecture Overview
📌 1. Android Architecture (Camera → JNI → C++ → OpenGL ES)
Camera2 API  
     ↓  
TextureView  
     ↓  
JNI (frame buffer)  
     ↓  
OpenCV C++ (Canny / Grayscale)  
     ↓  
Processed RGBA  
     ↓  
OpenGL ES Renderer  
     ↓  
Displayed on screen  

📌 2. Web Architecture (Webcam → TS/WASM → WebGL)
Webcam Stream  
     ↓  
HTML Canvas (Input)  
     ↓  
Edge Detection  
   • TypeScript (Sobel / Canny / etc.)  
   • OR OpenCV WebAssembly (optional)  
     ↓  
WebGL Renderer  
     ↓  
Browser Output  

📦 Project Structure
/android
   /app/src/main/java
   /app/src/main/cpp
   /gl
/web
   /src
   index.html
   package.json
   tsconfig.json
README.md
