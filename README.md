# Image-based Secure Data Embedding and Compression Using Huffman Coding and Histogram Shifting

A comprehensive steganography system that securely embeds and compresses data within color images using Huffman coding for optimal compression and histogram shifting algorithms for invisible data hiding.

## 🎯 What This Project Does

This system allows you to:
- **Hide secret text** inside regular images without visible changes
- **Compress data** before hiding to fit more information
- **Work with color images** instead of just grayscale
- **Analyze image quality** after data embedding
- **Check capacity** before encoding to choose the best cover image

## 🚀 Key Features

### Enhanced Data Hiding
- **Multi-channel encoding**: Uses all RGB channels instead of just one
- **3x capacity increase**: Significantly more data can be hidden compared to grayscale methods
- **Huffman compression**: Secret data is compressed before embedding for efficiency
- **Format flexibility**: Works with various image formats (PNG recommended)

### Security & Recovery
- **Secure keys**: Generates encryption keys (`enc_data.pkl`) for decoding
- **Frequency tables**: Acts as additional security layer for Huffman decoding
- **Lossless recovery**: Perfect reconstruction of hidden data

### Quality Analysis
- **PSNR calculation**: Measures signal quality after encoding
- **SSIM analysis**: Structural similarity assessment
- **MSE computation**: Mean square error evaluation
- **Capacity testing**: Pre-encoding capacity analysis

## 📁 Project Structure

```
├── Code/                   # Core implementation
│   ├── huffman.py         # Text compression/decompression
│   ├── histo-shift.py     # Image steganography engine
│   └── requirements.txt   # Dependencies
├── Analysis/              # Quality assessment tools
│   ├── main.py           # Combined analysis runner
│   ├── psnr.py           # Peak Signal-to-Noise Ratio
│   ├── ssim.py           # Structural Similarity Index
│   └── pvd.py            # Mean Square Error
└── README.md
```

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.x
- pip package manager

### Quick Install
```bash
# Clone the repository
git clone https://github.com/Sudeep72/Image-based-Secure-Data-Embedding-and-Compression-Using-Huffman-Coding-and-Histogram-Shifting.git
cd Image-based-SecureData-Embedding-and-Compression

# Install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

## 💻 Usage Guide

### Step 1: Compress Your Secret Data
```bash
python huffman.py
# Choose option 1 (Encoding)
# Input: secret_message.txt
# Output: encoded_binary.txt + frequency_table.pkl
```

### Step 2: Hide Data in Image
```bash
python histo-shift.py
# Choose option 1 (Encoding)
# Input: encoded_binary.txt + cover_image.png
# Output: encoded_image.png + enc_data.pkl
```

### Step 3: Check Image Quality (Optional)
```bash
python main.py original_image.png encoded_image.png
# Output: PSNR, SSIM, and MSE values
```

### To Recover Hidden Data:
```bash
# Step 1: Extract binary from image
python histo-shift.py
# Choose option 2 (Decoding)
# Input: encoded_image.png + enc_data.pkl
# Output: recovered_binary.txt

# Step 2: Decompress to original text
python huffman.py
# Choose option 2 (Decoding)  
# Input: recovered_binary.txt + frequency_table.pkl
# Output: recovered_message.txt
```

## 🔧 Tool Options

### Huffman Encoder (`huffman.py`)
- **Encoding**: Compress text files into binary format
- **Decoding**: Recover original text from binary + frequency table

### Histogram Shift Engine (`histo-shift.py`)
- **Encoding**: Embed binary data into cover images
- **Decoding**: Extract binary data from encoded images
- **Capacity**: Check maximum data capacity of any image

### Quality Analyzer (`main.py`)
- **PSNR**: Peak Signal-to-Noise Ratio measurement
- **SSIM**: Structural Similarity Index calculation  
- **MSE**: Mean Square Error analysis

## 📊 Performance Benefits

| Feature | Original Method | Enhanced Method |
|---------|----------------|-----------------|
| Color Support | Grayscale only | Full RGB |
| Data Capacity | Single channel | Triple capacity |
| Compression | None | Huffman encoding |
| Quality Analysis | Basic | Comprehensive |
| Security | Basic hiding | Multi-layer keys |

## 📈 Example Results

**Capacity Test Output:**
```
Testing image capacity...
cover1.png: 1,245,680 bits
cover2.png: 2,891,456 bits  
cover3.png: 856,320 bits
```

**Quality Analysis Output:**
```
Image Quality Analysis:
PSNR: 48.32 dB (Excellent)
SSIM: 0.9847 (Near Perfect)
MSE: 0.0023 (Very Low)
```

## 🔮 Future Enhancements

- [ ] Web-based user interface
- [ ] Advanced encryption integration
- [ ] Support for video steganography
- [ ] Real-time capacity optimization
- [ ] Batch processing capabilities

## 📝 Technical Notes

- **Recommended format**: PNG for optimal capacity and quality
- **Key files**: Always keep `enc_data.pkl` and `frequency_table.pkl` safe
- **Image size**: Larger images = higher data capacity
- **Compression ratio**: Varies based on text content repetition

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements!

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Project**: Image-based Secure Data Embedding and Compression Using Huffman Coding and Histogram Shifting  
**Technology Stack**: Python, OpenCV, NumPy, Matplotlib  
**Algorithms**: Huffman Coding, Histogram Shifting, RGB Channel Processing
