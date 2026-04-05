# Toluidine Blue ImageJ Macro
---
# **Quantitative Optical Density Analysis for Cartilage Histology**

**Aim**

This macro provides a standardised workflow for quantifying toluidine blue staining in cartilage using optical density (OD). It enables reproducible global and zonal analysis of staining intensity from histological images.

**Requirements**
- FIJI / ImageJ  
- RGB brightfield image of toluidine blue-stained cartilage  
- Visible white background region  

**Outputs**
- Tile-level OD measurements (Results table)  
- Global ROI intensity and OD  
- Mean ± SD for tile intensity and OD  
- ROI overlays and tile placement  
- Log summary of mean measurements  

---

## **How to Use**

**1. Open Image**

Open an RGB histology image in ImageJ.


**2. Run Macro**

Select:
- **GLOBAL** (full thickness, 60 tiles)  
- **ZONAL** (single zone, 20 tiles)  

Enter sample number and run number.


**3. Select Background (White Reference)**

Draw a rectangle over a white background region.

This is used to normalise intensity for OD calculation.


**4. Define Background Exclusion (Optional)**

Draw a polygon over background regions to exclude from analysis, i.e. the background above the sample.

Press OK to skip if not required.


**5. Define Exclusion Regions**

Draw:
- Lower exclusion region  
- Upper exclusion region  

Used to remove non-cartilage areas and define **zones**.


**6. Select Cartilage ROI**

Draw a rectangle around the cartilage region.
This defines the analysis area.


**7. Review Grayscale Image**

The macro converts the ROI to grayscale for analysis.


**8. Automatic Analysis**

The macro will:
- Calculate global intensity and OD  
- Randomly sample tiles (75 × 75 px)  
- Apply spacing and exclusion rules  
- Calculate tile-level OD  


**9. View Results**

- Results table contains tile data  
- ROI Manager stores tile locations  
- Overlay shows tile placement  
- Log window provides summary output

---  

## **Notes**

- If you are unable to accurately define cartilage zones due to degeneration/sample we encourage users use the GLOBAL macro option
- Image must be RGB at the start  
- Background selection directly affects OD  
- Use consistent imaging conditions across samples  
- ROI selection should reflect cartilage only  

---
