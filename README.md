# AI Photo Enhancer & Background Remover

A powerful web application that combines AI-powered image upscaling with automatic background removal functionality. This project enhances images up to 8x resolution while providing seamless background removal capabilities.

## 🌟 Features

- **AI Image Upscaling**: Enhance image resolution up to 8x (2x, 4x, 6x, 8x)
- **Automatic Background Removal**: Integrated background removal API
- **Drag & Drop Interface**: Easy file upload with drag-and-drop support
- **Real-time Preview**: Side-by-side comparison of original vs enhanced images
- **Multiple Format Support**: JPG, JPEG, PNG, BMP, WebP
- **Mobile Responsive**: Works seamlessly on desktop and mobile devices
- **Batch Processing**: Queue system for multiple image processing

## 📁 Project Structure

```
├── photo-upscaler-frontend/     # Frontend web application
│   ├── index.html              # Main HTML file
│   ├── css.css                 # Styling
│   ├── style.css               # Additional styles
│   ├── js_free-online-image-upscaler.js  # Main upscaler logic
│   ├── jsnew_image-upscaler.js # Enhanced image upscaler
│   ├── js_translation.js       # Internationalization
│   ├── js_FileSaver.js         # File download functionality
│   ├── js_spark-md5.min.js     # MD5 hash generation
│   ├── js_aes.js               # AES encryption
│   └── js_quene.js             # Queue management
├── python-backend/             # Python backend for background removal
│   ├── main.py                 # FastAPI backend server
│   ├── utils.py                # Utility functions
│   ├── requirements.txt        # Python dependencies
│   └── model/
│       └── model_q4.onnx       # Background removal model
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Modern web browser
- Internet connection (for upscaling API)

### Frontend Setup

1. Navigate to the frontend directory:
```bash
cd photo-upscaler-frontend
```

2. Open [`index.html`](photo-upscaler-frontend/index.html) in your web browser or serve it using a local server:
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .
```

3. Access the application at `http://localhost:8000`

### Backend Setup (Background Removal)

1. Navigate to the backend directory:
```bash
cd python-backend
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Run the backend server:
```bash
python main.py
```

The backend will start on `http://localhost:8080`

## 💻 Usage

### Image Upscaling

1. **Upload Image**: Click "Upload" or drag & drop an image file
2. **Select Magnification**: Choose from 2x, 4x, 6x, or 8x enhancement
3. **Process**: The image will be automatically processed using AI upscaling
4. **Download**: Save the enhanced image to your device

### Background Removal

- Background removal is automatically triggered after image upscaling
- The processed image with removed background will replace the upscaled result
- Use the save button to download the final image

### Supported Features

- **File Formats**: JPG, JPEG, PNG, BMP, WebP
- **Max Resolution**: Up to 99,000 x 99,000 pixels
- **Drag & Drop**: Support for drag and drop file upload
- **Mobile Support**: Touch-friendly interface for mobile devices

## 🔧 Configuration

### Frontend Configuration

Key configuration files:
- [`js_free-online-image-upscaler.js`](photo-upscaler-frontend/js_free-online-image-upscaler.js) - Main upscaling logic and API integration
- [`jsnew_image-upscaler.js`](photo-upscaler-frontend/jsnew_image-upscaler.js) - Enhanced UI components

### Backend Configuration

- [`main.py`](python-backend/main.py) - FastAPI server configuration
- [`utils.py`](python-backend/utils.py) - Background removal utilities
- [`model/model_q4.onnx`](python-backend/model/model_q4.onnx) - AI model for background removal

## 🌐 API Integration

### Upscaling API
The frontend integrates with an external upscaling service:
```javascript
// Example API call from js_free-online-image-upscaler.js
$.ajax({
    url: "https://ai-api.free-videoconverter.net/v4/sr/sr",
    type: "post",
    data: formData,
    success: function(response) {
        // Handle upscaled image
    }
});
```

### Background Removal API
Local Python backend handles background removal:
```javascript
// Automatic background removal integration
window.sendToBackgroundRemovalAPI = async function(imageUrl) {
    // Process image through local backend
};
```

## 🛠️ Development

1. **Frontend**: Modify JavaScript files in [`photo-upscaler-frontend/`](photo-upscaler-frontend/)
2. **Backend**: Update [`main.py`](python-backend/main.py) or [`utils.py`](python-backend/utils.py)
3. **Styling**: Edit [`css.css`](photo-upscaler-frontend/css.css) or [`style.css`](photo-upscaler-frontend/style.css)



## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request


## 🙏 Acknowledgments

- **Qoc Upscaler** by free-videoconverter.net for the base upscaling functionality
- **ONNX Runtime** for background removal model inference
- **FastAPI** for the backend framework

## 📞 Support

For issues or questions:
1. Check the browser console for error messages
2. Ensure all dependencies are installed
3. Verify internet connection for upscaling API
4. Check that the backend server is running for background removal

---

*"Great Software, horrible interface" - Now with a better interface! 😄*