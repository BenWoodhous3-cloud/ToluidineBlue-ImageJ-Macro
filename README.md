# ToluidineBlue-ImageJ-Macro
Semi-automated ImageJ macro for quantitative optical density analysis of toluidine blue staining in cartilage histology. Includes background normalisation, ROI selection, and random tile sampling for reproducible global and zonal assessment.

**Introduction**

Toluidine blue is a metachromatic stain widely used in cartilage histology to visualise sulphated glycosaminoglycans (sGAGs) within the extracellular matrix. Regions with higher sGAG content exhibit increased dye binding and darker staining, reflecting matrix composition and tissue health.

This repository provides a semi-automated ImageJ macro that converts toluidine blue staining into quantitative optical density (OD) measurements. The workflow incorporates background normalisation, user-defined regions of interest (ROIs), and randomised tile sampling to enable reproducible global and zonal analysis of cartilage structure.

**Optical Density & Quantification Approach**

Staining intensity is quantified using OD, which describes light absorbance and is derived from the Beer-Lambert law. In this context, OD reflects the relative accumulation of toluidine blue within the tissue.

**OD=log10​(I/I0​​)**

Where:

**I0**=background (incident) light intensity

**I**=transmitted light intensity through the stained tissue

Darker staining corresponds to lower transmitted light and therefore higher OD values, indicating greater sGAG content. By applying this principle to grayscale image data, the macro enables objective, continuous quantification of cartilage matrix staining while preserving spatial variation across tissue regions.

![BW](https://github.com/user-attachments/assets/bda7ce57-e08b-413a-b7ec-15a74b8fce6e)
**Figure 1.** Multiscale structural organisation of articular cartilage and molecular staining with toluidine blue. Schematic representation of articular cartilage and extracellular matrix (ECM) components across hierarchical length scales, from macroscale tissue architecture to picoscale interactions. At the macroscale, the osteochondral unit is shown, highlighting the articular cartilage surface and underlying subchondral bone. The microscale illustrates zonal cartilage organisation with embedded chondrocytes distributed within the ECM. At the nanoscale, the ECM ultrastructure is depicted, comprising a network of collagen fibrils interwoven with proteoglycans (PGs) and hyaluronan. The picoscale highlights molecular interactions, including sulphated glycosaminoglycan (sGAG) chains within PGs and their electrostatic binding with the cationic dye toluidine blue. The lower panel details key components: articular cartilage, chondrocytes, hyaluronan backbone, collagen fibrils, and proteoglycan aggregates formed via link proteins. Toluidine blue binding to negatively charged sGAGs results in metachromatic staining, represented by monomeric, dimeric, and trimeric dye associations, reflecting increasing levels of molecular aggregation and charge interaction. Figure created in BioRender11.
