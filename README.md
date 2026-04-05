# ToluidineBlue-ImageJ-Macro
Semi-automated ImageJ macro for quantitative optical density analysis of toluidine blue staining in cartilage histology. Includes background normalisation, ROI selection, and random tile sampling for reproducible global and zonal assessment.

**Introduction**
Toluidine blue is a metachromatic stain widely used in cartilage histology to visualise sulphated glycosaminoglycans (sGAGs) within the extracellular matrix. Regions with higher sGAG content exhibit increased dye binding and darker staining, reflecting matrix composition and tissue health.
This repository provides a semi-automated ImageJ macro that converts toluidine blue staining into quantitative optical density (OD) measurements. The workflow incorporates background normalisation, user-defined regions of interest (ROIs), and randomised tile sampling to enable reproducible global and zonal analysis of cartilage structure.

**Optical Density & Quantification Approach**
Staining intensity is quantified using OD, which describes light absorbance and is derived from the Beer-Lambert law. In this context, OD reflects the relative accumulation of toluidine blue within the tissue.
OD=log10​(I/I0​​)
Where:
I0=background (incident) light intensity
I=transmitted light intensity through the stained tissue
Darker staining corresponds to lower transmitted light and therefore higher OD values, indicating greater sGAG content. By applying this principle to grayscale image data, the macro enables objective, continuous quantification of cartilage matrix staining while preserving spatial variation across tissue regions.
