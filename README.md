# 💻👤👤 BgReplace-DeepLabv3-AlphaBlending-for-InVideo-background-replacement
This repo is an attempt at reverse engineering the background replacement feature offered by video conferencing sites like zoom. DeepLabv3 was used for precise foreground mask computation and the extracted foreground was elegantly fused with the background image/gif by an old school computer vision technique called AlphaBlending.

# Demo 👇
<video src="demo.mp4" controls width="640"></video>
[[Link to Demo]](https://youtu.be/RqFwmqA6Rvw "Click to watch")

# Overview of the pipeline
![Alt text](Full_Pipeline.png)

## 🚀 Features

* **AlphaBlending or Alpha Composition**: Used to generate the **alpha mask** that seamlessly merges foreground and background.
* **DeepLabv3**: Effective **foreground Segmentation**.
* **Real time blending**: Of foreground with the background image using the generated **alpha mask**.
---

## 📂 Project Structure

```bash
.
├── live_frame_cache/         # Folder cache where the current frame & its computed alpha mask sit before blending.
├── bg/                       # Test gif for background-foreground merging.
    ├── underwater.gif                    
├── models/                   # DeepLabv3 checkpoint.
      ├── deeplabv3.pth
├── office_test_images/       # Some test scenes from the show - "The Office" to be supplied for inference.
├── requirements.txt          # Python dependencies.
├── deeplabv3.py              # A Streamlit demo of the entire project.
├── PersonFg_Segmentation.ipynb   # Implements the entire Foreground segmentation + AlphaBlending Pipeline.
├── Full_Pipeline.png         # Architecture diagram of DeepLabv3 based Foreground segmentation + AlphaBlending Pipeline.
```

---
