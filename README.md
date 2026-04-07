# Toluidine Blue ImageJ Macro
---
# **Quantitative Optical Density Analysis for Cartilage Histology**

**Aim**

This macro provides a standardised and reproducible workflow for quantifying toluidine blue staining in cartilage using optical density (OD). It supports both whole-sample (global) and region-specific (zonal) analysis of histological images.

**Requirements**
To run the macro, you will need:
- FIJI / ImageJ  
- RGB brightfield image of toluidine blue-stained cartilage  
- Visible white background region  

**Outputs**
Running the macro will generate:
- Tile-level optical density measurements (Results table)
- Global ROI intensity and OD values
- Mean ± standard deviation for tile intensity and OD
- ROI overlays showing tile placement
- A log summary of key measurements 

---

## **WORKFLOW**

**1. Open Image**

Load your RGB histology image into ImageJ.


**2. Run Macro**


<img width="930" height="850" alt="Screenshot 2026-04-06 at 09 37 54" src="https://github.com/user-attachments/assets/677d272a-bbf1-4e3b-9a79-ebb465d422bd" />


Select the analysis type:
- **GLOBAL** (full cartilage depth, 60 tiles)  
- **ZONAL** (specific cartilage zone, 20 tiles) 
 

Enter your sample number and run number when prompted.



**GLOBAL**



<img width="934" height="845" alt="Screenshot 2026-04-06 at 09 41 23" src="https://github.com/user-attachments/assets/f3339392-e8fc-467d-898f-91c0e6c28388" />



**ZONAL**



<img width="933" height="847" alt="Screenshot 2026-04-06 at 09 39 27" src="https://github.com/user-attachments/assets/2b811b57-da1a-4d36-87ce-3c6d6ff8cd65" /> 
<img width="237" height="416" alt="Screenshot 2026-04-06 at 09 40 23" src="https://github.com/user-attachments/assets/859b3b21-6cde-417a-9d58-1c32d0809ca6" />




**3. Select Background (White Reference)**

Draw a rectangle over a clean white background area.

This step is essential, as it is used to normalise intensity values for optical density calculations.

Tip: Close small white balance windows if needed, but keep the main image and analysis windows open.


<img width="939" height="846" alt="Screenshot 2026-04-06 at 09 45 19" src="https://github.com/user-attachments/assets/903055e7-38b0-437d-9690-f4b82391896c" />



**4. Define Background Exclusion (Optional)**

If there are unwanted background regions (e.g. above the sample), draw a polygon to exclude them.

If no exclusion is needed, simply press **OK** to continue.


<img width="1470" height="845" alt="Screenshot 2026-04-06 at 09 49 15" src="https://github.com/user-attachments/assets/5316946f-cdb5-4a4a-9cfd-8aa646e8e428" />



**5. Define Exclusion Regions**

You will now define the vertical limits of your analysis:

- Lower exclusion region

**GLOBAL**: set at the tidemark (end of deep zone)

<img width="1468" height="845" alt="Screenshot 2026-04-06 at 09 52 57" src="https://github.com/user-attachments/assets/58abf49c-ea62-42b4-8b69-8a37ae00afef" />


**ZONAL**: set at the bottom of the selected zone

<img width="932" height="844" alt="Screenshot 2026-04-07 at 11 51 51" src="https://github.com/user-attachments/assets/caf6824b-aafa-48c0-b05a-f9d16174f171" />


- Upper exclusion region

**GLOBAL**: set at the cartilage surface (top of sample)

<img width="1470" height="843" alt="Screenshot 2026-04-06 at 09 53 37" src="https://github.com/user-attachments/assets/bb09c233-0bde-429e-a32d-1cfa19acc06d" />


**ZONAL**: set at the top of the selected zone

![Screenshot 2026-04-07 at 11 52 42](https://github.com/user-attachments/assets/300e300b-23a8-413a-b80e-ef378b6ac53b)

 
These boundaries ensure tiles are placed only within the region of interest.

**6. Select Cartilage ROI**

Draw a rectangle around the cartilage area you want to analyse.

For best results, include the full cartilage region to ensure a representative analysis. Although exclusion zones are already defined, this ROI should encompass all relevant tissue.


<img width="1467" height="842" alt="Screenshot 2026-04-06 at 09 54 01" src="https://github.com/user-attachments/assets/cc5aefb2-0331-4310-afbe-35af36edbd5e" />


**7. Review Grayscale Image**

The macro converts your ROI into grayscale images for analysis. You will see:

- A standard 8-bit image
- A masked 8-bit image reflecting exclusion regions

Use these images to visually confirm that tile placement has occured only within cartilage.

<img width="1470" height="841" alt="Screenshot 2026-04-06 at 09 59 01" src="https://github.com/user-attachments/assets/3dcc2f14-75db-40e9-a93e-4f3181131155" />

![Screenshot 2026-04-07 at 11 58 38](https://github.com/user-attachments/assets/578dc446-3bdf-4823-87b8-31fe69046a55)


At this stage:

- Remove overlays if needed and replace from the same drop down section **from ROI manager**
- Use the ROI Manager to inspect or adjust ROIs
- Delete any ROIs placed on artefacts (e.g. folds or tears)

<img width="1470" height="843" alt="Screenshot 2026-04-06 at 10 01 37" src="https://github.com/user-attachments/assets/5d84ed44-65fc-4c2f-95ea-fa0827440cf7" />


You can also use the ROI Manager to review individual ROIs or adjust their appearance (e.g. colour) by selecting the ROI(s) and clicking **“Properties”**.


<img width="1470" height="843" alt="Screenshot 2026-04-06 at 10 04 51" src="https://github.com/user-attachments/assets/f79b2175-cac3-4076-9583-4df9d6c62754" />

At this stage for the **ZONAL** th user must remove all overlay from the RGB image and **RE-RUN** the analysis on the sequential zone. Ensuring zonal analysis in the 

**SUPERFICIAL**: YELLOW

**MIDDLE**: CYAN

**DEEP**: GREEN

<img width="1452" height="846" alt="Screenshot 2026-04-07 at 12 38 34" src="https://github.com/user-attachments/assets/8575b36c-8a64-4dcb-958b-195be9e76494" />


**8. AUTOMATIC ANALYSIS**

The macro will now:

- Calculate CARTILAGE GLOBAL mean intensity and mean optical density with Standard deviation (i.e. non random ROI placement)
- Randomly generate ROI "TILES" (75 × 75 px)
- Apply spacing and exclusion rules
- Compute OD for each tile as well as a mean of the X amount of ROI.

**9. VIEW & EXPORT RESULTS**

Outputs are displayed across several panels:

- Results table: tile-level data
- ROI Manager: tile locations
- Overlay: visual tile placement
- Log window: summary statistics (mean ± SD)

Each tile includes:
- X and Y coordinates
- Sample and run identifiers
- Analysis type and zone
- Mean intensity
- Optical density (OD)

We recommend exporting results as a .csv or Excel file for downstream analysis.
R (e.g. RStudio) is well suited for further statistical analysis.

<img width="1470" height="842" alt="Screenshot 2026-04-06 at 10 08 33" src="https://github.com/user-attachments/assets/8bb5813e-62bf-475b-812d-2aaded8891e2" />



---  

## **Notes**

- If cartilage zones cannot be clearly defined (e.g. due to degeneration), use the GLOBAL option
- Images must be RGB before running the macro. We also recommend using non-cpmpressed RAW/TIF images, as condensed JPEG images may yield less robust results.
- Background selection directly influences OD calculations
- Maintain consistent imaging conditions across samples
- Ensure ROI selection includes cartilage only
