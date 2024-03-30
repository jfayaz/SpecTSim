# Spectrally-Targeted Time-Series Simulator (SpecTSim)


Note: This tool requires working internet connection and Matlab-Runtime (9.4) (https://www.mathworks.com/products/compiler/matlab-runtime.html) installed in the PC.


This tool simulates site-based synthetic ground-motions using DRD (aka ADK) simulation model (Razaeian et. al. 2012,  Dabaghi et. al. 2018b) that match a Target Spectrum. The tool provides two options: 1) Provide the Target Spectrum csv file or 2) Use Uniform Hazard Spectrum (UHS) obtained from Unified Hazard Tool (2008) of USGS as the Target Spectrum. The tool uses the algorithm proposed by Fayaz and Zareian (submitted) to simulate site-based ground motion whose RotD50 spectrum naturally matches the Target Spectrum between specified range of periods.


Instructions:

The primary inputs to this tool include: 'Edition', 'Longitude', 'Latitude', 'Vs30 (m/s)', 'Period of Structure (T*)', 'Period Scale Factor 1 (PSF1)', 'Period Scale Factor 2 (PSF2)', 'Hazard Level', 'Required Number of GMs (n)' and 'Index of Agreement (IA)'. 'Edition', 'Longitude', 'Latitude', 'Vs30 (m/s)', 'Period of Structure (T*)', and 'Hazard Level' are used to obtain Deaggregation and Hazard Curves from the USGS Unified Hazard Tool (2008). The data obtained from USGS is combined with Cybershake-UCERF2 database to randomize Near-Fault Parameters (NFP) of the DRD model (Dabghi et al 2018a). These are used to simulate the 'n' GMs using Fayaz and Zareian (2021). For the option: 'Do you wish to provide Target Spectrum', if the user selects 'Yes', then the options of 'Target Spectrum file', 'Mw', and 'Rrup' get activated. With this option, the ground motions are simulated using inputted *Mw* and *Rrup* and the inputted csv file containing the Target Spectrum is used as the target to match. An example Target Spectrum file, 'Target Spectrum.csv', file is provided within the folder of this tool. Column A of the csv file should contain the periods and Column B should contain the corresponding RotD50 Sa. If the user selects 'No', then UHS downloaded from the USGS UHT (2008) is used as the Target Spectrum. In both cases, the ground motions are simulated such that they naturally match the Target Spectrum between periods *PSF1xT* (sec) and *PSF2xT* (sec) gauged by 'Index of Agreement (IA)' using Fayaz and Zareian (2021). IA values range between 0 and 1. IA = 1 means perfect match and IA = 0 means no match at all. 0.8 < IA < 0.9 is recommended for an efficient match.



Seed No.' is an input for randomness and reproducibility; must be a whole number. It will be concatenated to the input of 'Name of folder to contain results output' for creating the folder for results. The format of the results folder name will be as: 'Name of folder to contain results output-Seed No.'



USGS currently possess Hazard Curves and Deaggregation only for PGA and Periods = 0.2, 1.0, & 2.0 sec and Vs30 = 180, 259, 360, 537, 760 & 1150 m/s. Hence the Hazard Curves are generated only for these Periods and Deaggregation is conducted for the Period closest to the Period entered by the user.



    Primary citation for this tool :    
    Jawad Fayaz and Farzin Zareian (2021). "An Efficient Algorithm to Simulate Site-Based Ground Motions that match a Target Spectrum". Earthquake Engineering and Structural Dynamics, Vol. 50, Issue 13, Pages 3532-3549


References:

1) Fayaz J., and Zareian F. (2021). An Efficient Algorithm to Simulate Site-Based Ground Motions that match a Target Spectrum. Earthquake Engineering and Structural Dynamics, Vol. 50, Issue 13, Pages 3532-3549.

2) Fayaz J., Azar S., Dabaghi M., and Zareian F. (2020). An Efficient Algorithm to Simulate Hazard-Targeted Site-Based Synthetic Ground Motions, Earthquake Spectra, Vol. 37, Issue 2, Pages 876-902.

3) Dabaghi, M., Daoud, Y., and Der Kiureghian, A. (2018a). Simulation of near fault ground motions for randomized hypocenter and site locations, Proceedings of the 11th US National Conference on Earthquake Engineering, Los Angeles, CA.

4) Dabaghi M., and Der Kiureghian A. (2018b). Simulation of orthogonal horizontal components of near‐fault ground motion for specified earthquake source and site characteristics. Earthquake Engineering & Structural Dynamics; 47(6):1369-1393.

5) Rezaeian, S., and Der Kiureghian, A. (2012). Simulation of orthogonal horizontal ground motion components for specified earthquake and site characteristics. Earthquake Engineering & Structural Dynamics; 41(2), 335-353.
