
# 🌍 Environmental Impact Analysis using Satellite Data

This project uses satellite data to analyze environmental changes over time. By leveraging image processing techniques, we aim to monitor and quantify environmental impacts such as deforestation, urban sprawl, and water body shrinkage. The analysis provides a valuable tool for researchers, policy-makers, and environmentalists to make data-driven decisions.


## 📁 Project Structure

Environmental\_Impact\_Analysis\_using\_Satellite\_Data.ipynb
README.md
requirements.txt (optional)

## 📌 Features

- 📷 **Satellite Image Comparison**: Analyze before-and-after satellite images to detect environmental changes.
- 🧠 **Image Processing**: NDVI (Normalized Difference Vegetation Index) and other spectral indices for vegetation and land analysis.
- 📊 **Change Detection**: Visualize land cover changes using Python libraries.
- 🗺️ **Region-Specific Analysis**: Tailor analysis to a specific geographic location using pre-processed satellite data.


## 🛠️ Technologies Used

- Python 3.x  
- NumPy  
- OpenCV  
- Matplotlib  
- Rasterio  
- EarthPy (if used)  
- GDAL (optional)


## 🚀 How to Run

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/environmental-impact-analysis.git
   cd environmental-impact-analysis


2. **Install Dependencies**
   *(If `requirements.txt` exists)*

   ```bash
   pip install -r requirements.txt
   ```

3. **Launch Jupyter Notebook**

   ```bash
   jupyter notebook Environmental_Impact_Analysis_using_Satellite_Data.ipynb
   ```

---

## 📂 Input Data

The notebook uses pre-downloaded satellite images of the same region taken at different times (e.g., before and after a natural disaster or over a span of years). Ensure the following:

* Images are georeferenced
* File formats: `.tif`, `.jpg`, or `.png`
* Place them in the appropriate directory or update paths in the notebook

---

## 📈 Example Use-Cases

* Deforestation monitoring (Amazon, Indonesia)
* Urban expansion (Lahore, Karachi)
* Flood impact analysis (Sindh, Punjab)
* Glacier retreat observation (Karakoram, Himalayas)

---

## 📌 Future Improvements

* Integrate Google Earth Engine for real-time data
* Automate preprocessing of raw satellite imagery
* Add support for time-series animation of environmental change

---

## 🧑‍💻 Author

**Shahzeb Faisal**
📧 [l215649@lhr.nu.edu.pk](mailto:l215649@lhr.nu.edu.pk)
🔗 [LinkedIn](https://www.linkedin.com/in/shahzeb-faisal-8b9190321/)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
