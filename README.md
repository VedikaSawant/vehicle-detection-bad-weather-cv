# 🚗 Vehicle Detection in Adverse Weather Using Computer Vision

This project implements a real-time vehicle detection pipeline for foggy and low-visibility conditions using a combination of classical and deep learning computer vision techniques. The system is optimized for static camera environments such as traffic monitoring or security surveillance and produces annotated output as video frames or a GIF.

---

## 🎯 Objective

To detect and localize **moving vehicles in foggy conditions** by enhancing contrast, applying semantic segmentation, and filtering background motion — all without any supervised training.

---

## 📌 Features

- ✅ **Fog Enhancement** using CLAHE (Contrast Limited Adaptive Histogram Equalization)
- ✅ **Semantic Segmentation** using DeepLabV3 with ResNet101 (PyTorch)
- ✅ **Motion Detection** using OpenCV’s MOG2 background subtractor
- ✅ **Contour Filtering & Bounding Boxes** for object localization
- ✅ **Optimized Processing** with frame skipping and resolution resizing
- ✅ **GIF Export** for visualizing results

---

## 📸 Input vs Output

| Input (Foggy Footage) |
|----------------------------|
 

https://github.com/user-attachments/assets/5fa04fb9-5ef8-4cbc-9aa2-6eeba5715703

| Output (Detected Vehicles) |
|----------------------------|
![vehicle detection output](https://github.com/VedikaSawant/vehicle-detection-bad-weather-cv/blob/main/media/vehicle%20detection%20output.gif)

---

## 🧠 Pipeline Overview

1. **Frame Preprocessing**
   - Apply CLAHE to enhance contrast in foggy scenes.
   - Resize frames for efficient segmentation.

2. **Semantic Segmentation**
   - Use DeepLabV3 to extract vehicle-relevant pixels (car, bus, truck).

3. **Background Subtraction**
   - Apply MOG2 subtractor to isolate moving regions.
   - Threshold and morphologically filter foreground mask.

4. **Mask Fusion**
   - Combine segmentation mask and motion mask to extract only **moving vehicles**.

5. **Object Detection**
   - Filter small blobs.
   - Draw bounding boxes around valid vehicle contours.

---

## ⚙️ Technologies and Tools Used

- `Python`
- `OpenCV`
- `PyTorch`
- `DeepLabV3 (ResNet101 pretrained)`
- `Google Colab`

---

## 📊 Performance Highlights

- 🚗 Accurate vehicle detection in low-visibility (foggy) scenes
- ⚡ Optimized with frame skipping and resolution control
- 🧹 Effective noise reduction via morphology and filtering

---

## 🧪 Limitations

- Assumes **static camera** (ideal for fixed CCTV or traffic poles)
- Sensitive to abrupt lighting changes (e.g., car headlights)
- May struggle in crowded or highly dynamic scenes

---

## 🌍 Real-World Applications

- 🚦 Traffic surveillance (e.g., fog-prone highways)
- 🏠 Home security systems
- 🚢 Port & maritime object detection

---

## 🔭 Future Scope

- **Multi-Weather Support**: Extend detection to rainy, snowy, and low-light/night-time conditions using specialized enhancement techniques.
- **Deep Learning Enhancements**: Integrate optical flow or train segmentation models on weather-specific datasets for improved accuracy.
- **Edge Deployment**: Optimize the pipeline for real-time inference on devices like NVIDIA Jetson or Raspberry Pi.
- **Vehicle Tracking & Analytics**: Add multi-object tracking and traffic analytics for smart surveillance applications.

---

## 📚 References

- [PeerJ CS Research Paper](https://peerj.com/articles/cs-962/)
- [OpenCV Documentation](https://docs.opencv.org/)
- [PyTorch DeepLabV3 Docs](https://pytorch.org/vision/stable/models.html#semantic-segmentation)
