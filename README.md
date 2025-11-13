🚀 Real-Time Edge Detection Viewer
🎯 Android (OpenCV C++ + OpenGL ES + JNI) + Web (TypeScript)

This project demonstrates a real-time edge detection pipeline using OpenCV in C++, rendered via OpenGL ES, with a companion TypeScript Web Viewer for visualization.
It showcases native processing, GPU rendering, and cross-platform integration — all in one lightweight system.

✅ Features Implemented (Android + Web)
🔹 📱 Android Application

✔️ Camera feed integration using Camera2 API + TextureView
✔️ Frame processing in OpenCV C++ via JNI
✔️ Supported filters:
    • 🟦 Grayscale
    • ⚡ Canny Edge Detection
✔️ Real-time GPU rendering using OpenGL ES 2.0 textures
✔️ Smooth performance (10–15 FPS guaranteed)
✔️ Bonus feature:
    • 🔄 Toggle between Raw Feed ↔ Processed Feed

🔹 🌐 Web Viewer (TypeScript + WebGL)

✔️ Browser webcam integration
✔️ Edge detection algorithms implemented in TS:
    • Sobel
    • Canny
    • Prewitt
    • Roberts
    • Laplacian
✔️ Optional OpenCV WebAssembly backend
✔️ GPU-accelerated rendering with WebGL
✔️ Displays:
    • Processed output frame
    • FPS counter & resolution info

📷 Screenshots / GIFs

(Add your own screenshots here)

![Android App](screenshots/android.png)
![Web Viewer](screenshots/web.png)


💡 Tip: Use screen recordings for bonus impact!

⚙️ Setup Instructions
📱 Android Setup (NDK + OpenCV)
🛠 Requirements

Android Studio

Android NDK

OpenCV Android SDK

Physical Android device (recommended)

📌 Steps

Install & enable NDK in Android Studio

Download OpenCV-Android-SDK

Place OpenCV here:

app/src/main/cpp/opencv/


Update CMakeLists.txt to link OpenCV

Build and run the app

🌐 Web Viewer Setup (TypeScript)
Install dependencies:
npm install
npm run build

Run local dev server:
npm run serve


OR

python3 serve.py

Open the viewer:

👉 http://localhost:8000

🧠 Architecture Overview
🔧 1. Android Frame Pipeline
Camera2 API  
     ↓  
TextureView  
     ↓  
JNI (frame buffer transfer)  
     ↓  
OpenCV C++ (Grayscale / Canny)  
     ↓  
Processed RGBA output  
     ↓  
OpenGL ES Renderer  
     ↓  
📱 Display

🔧 2. Web Viewer Pipeline
Webcam Stream  
     ↓  
HTML Canvas  
     ↓  
Edge Detection (TS or WASM OpenCV)  
     ↓  
WebGL Renderer  
     ↓  
🌐 Browser Output

📦 Project Structure
/android
   /app/src/main/java      → Java/Kotlin code
   /app/src/main/cpp       → OpenCV C++ + JNI
   /gl                     → OpenGL ES renderer
/web
   /src                    → TypeScript logic
   index.html
   package.json
   tsconfig.json
README.md
