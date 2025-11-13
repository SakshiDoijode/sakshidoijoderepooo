🔍 Real-Time Edge Detection Viewer
Android (OpenCV C++ + OpenGL ES + JNI) + Web (TypeScript)

This project implements a real-time edge detection pipeline using OpenCV in C++, rendered using OpenGL ES, with a companion TypeScript Web Viewer for visualization. The system demonstrates native processing, GPU rendering, and cross-platform integration between Android and Web.

What’s Included (Implemented)
Web Implementation

Real-time webcam processing using TypeScript with multiple algorithms:

Sobel, Canny, Prewitt, Roberts, Laplacian

Implementations inside: EdgeDetector.sobel and EdgeDetector.canny

OpenCV C++ via WebAssembly wrapper:

OpenCVProcessor.initialize

GPU rendering using WebGL (OpenGL ES 2.0):

WebGLRenderer.render

Main application glue:

EdgeDetectionApp

Key Files

src/app.ts

src/edge-detection.ts

src/opencv-processor.ts

src/webgl-renderer.ts

src/types.ts

index.html

serve.py

package.json

tsconfig.json

Features Implemented (Android + Web)
Android Application

Camera feed integration using Camera2 API + TextureView

Frame processing in OpenCV C++ via JNI

Supported filters:

Grayscale

Canny Edge Detection

Real-time GPU rendering using OpenGL ES 2.0 textures

Smooth performance (10–15 FPS)

Bonus:

Toggle between Raw Feed ↔ Processed Feed

Web Viewer (TypeScript + WebGL)

Browser webcam integration

Multiple edge-detection algorithms implemented in TypeScript:

Sobel, Canny, Prewitt, Roberts, Laplacian

Optional WebAssembly-based OpenCV backend

GPU-accelerated rendering using WebGL

Viewer displays:

Processed output frame

FPS counter

Resolution information

Screenshots / GIFs

(Add your own screenshots here.)

screenshots/android.png  
screenshots/web.png

Setup Instructions
Android Setup (NDK + OpenCV)
Requirements

Android Studio

Android NDK

OpenCV Android SDK

Physical (recommended) or virtual device

Steps

Enable NDK in Android Studio

Download and extract OpenCV-Android SDK

Place OpenCV folder inside:

app/src/main/cpp/opencv/


Update CMakeLists.txt to link OpenCV

Build and run the project

Web Viewer Setup (TypeScript)
Install dependencies:
npm install
npm run build

Start development server:
npm run serve


Or:

python3 serve.py


Open in browser:
http://localhost:8000

Architecture Overview
Android Data Flow (Camera → JNI → OpenCV C++ → OpenGL ES)
Camera2 API  
       ↓  
TextureView  
       ↓  
JNI (frame buffer)  
       ↓  
OpenCV C++ (Grayscale / Canny)  
       ↓  
Processed RGBA buffer  
       ↓  
OpenGL ES Renderer  
       ↓  
Display Output  

Web Data Flow (Webcam → TypeScript/WASM → WebGL)
Webcam  
       ↓  
HTML Canvas  
       ↓  
Edge Detection Logic  
   - TypeScript Algorithms  
   - OR OpenCV WebAssembly  
       ↓  
WebGL Renderer  
       ↓  
On-Screen Output  

Project Structure
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
