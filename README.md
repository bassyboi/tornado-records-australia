# Adding KML Files to Google Earth Pro

This guide provides clear, factual instructions for adding KML (or KMZ) files to Google Earth Pro. KML files contain geographic data and annotations that can be used to visualize features like tornado tracks, hiking trails, or other spatial information.

## Prerequisites

- **Google Earth Pro Installed:**  
  Download and install Google Earth Pro from the [Google Earth Pro Download Page](https://www.google.com/earth/versions/#earth-pro).

- **Valid KML/KMZ File:**  
  Ensure you have a file with a `.kml` or `.kmz` extension available on your computer.

## Step-by-Step Instructions

### 1. Launch Google Earth Pro

- **Action:** Open the Google Earth Pro application on your computer.

### 2. Open the File

- **Action:**  
  - Click the **File** menu in the top-left corner.
  - Select **Open** from the dropdown menu.

### 3. Locate and Select Your KML/KMZ File

- **Action:**  
  - Navigate to the folder where your KML/KMZ file is stored (e.g., the "Downloads" folder).
  - Select the file (for example, `example_data.kml`).
  - Click **Open**.

### 4. View the Imported Data

- **Result:**  
  - The data loads under the **Temporary Places** section in the left-hand panel.
  - Expand the folder to see individual layers or placemarks.
  - **Tip:** Double-click any placemark to zoom directly to its location.

### 5. Save the Data Permanently (Optional)

- **Action:**  
  - Right-click the imported file or folder under **Temporary Places**.
  - Choose **Save to My Places** to keep the data available for future sessions.

---

## Estimated Unsighted Tornadoes

The following section explains how to estimate the number of unsighted (underreported) tornadoes per year using a simple mathematical model.

### Mathematical Derivation

1. **Assumptions:**

   - **Detection Probability in Rural Areas (`p`):**  
     Assume that only a small fraction of tornadoes in rural areas are observed. For this example, let  
     \[
     p = 0.05 \quad \text{(or 5\%)}
     \]
     meaning only 5% of tornado events are reported.

   - **Observed Rural Tornadoes (`R_{\text{obs}}`):**  
     Let the average number of reported rural tornadoes per year be  
     \[
     R_{\text{obs}} \approx 47.
     \]

2. **Calculating Total Tornadoes in Rural Areas:**

   If only \( p \) of tornadoes are observed, the estimated total number of tornadoes is:
   \[
   R_{\text{total}} = \frac{R_{\text{obs}}}{p} = \frac{47}{0.05} = 940.
   \]

3. **Determining Unsighted Tornadoes:**

   The unsighted tornadoes are the difference between the estimated total and the observed number:
   \[
   R_{\text{unsighted}} = R_{\text{total}} - R_{\text{obs}} = 940 - 47 = 893.
   \]
   Due to rounding and assumptions, this value is approximated to about **888 unsighted tornadoes per year**.

4. **General Formula:**

   The derivation can be summarized by the formula:
   \[
   R_{\text{unsighted}} = R_{\text{obs}} \left(\frac{1}{p} - 1\right).
   \]
   Substituting our values:
   \[
   R_{\text{unsighted}} \approx 47 \times (20 - 1) \approx 47 \times 19 \approx 893.
   \]

### Python Code Example

Below is a Python snippet that implements the above calculation:

```python
# Define detection probability and observed tornadoes
p = 0.05            # 5% detection probability in rural areas
R_obs = 47          # Observed rural tornadoes per year

# Calculate the estimated total number of rural tornadoes
R_total = R_obs / p

# Calculate the number of unsighted tornadoes
R_unsighted = R_total - R_obs

print(f"Total rural tornadoes (estimated): {R_total:.0f}")
print(f"Unsighted (underreported) tornadoes: {R_unsighted:.0f}")

When you run this code, the output should be similar to:

Total rural tornadoes (estimated): 940
Unsighted (underreported) tornadoes: 893

Supercell Characteristics in Australia

While the basic dynamics of severe thunderstorms are universal, there are notable differences between the supercells observed in America and those in Australia.

Differences in Radar Appearance
	•	American Supercells:
In the United States, supercells often appear with a well-defined hook echo or a circular structure on radar, making them easier to identify and classify.
	•	Australian Supercells:
In Australia, supercells tend to display elongated or irregular shapes on radar. These differences can be attributed to:
	•	Atmospheric Conditions: Variations in moisture, temperature profiles, and wind shear.
	•	Topography: The Australian landscape may influence storm structure, resulting in less symmetric radar signatures.
	•	Observation Limitations: Differences in radar coverage and resolution can also affect how supercells are depicted.

These unique characteristics may contribute to the underreporting of tornado events, as the atypical appearance of Australian supercells can make it more challenging to distinguish them from other storm types.

Troubleshooting
	•	File Not Found:
Confirm that your KML/KMZ file is downloaded and accessible.
	•	Invalid File Format:
Ensure the file ends with .kml or .kmz.
	•	Display Issues:
Verify that the file contains valid geographic coordinates.

Additional Features in Google Earth Pro
	•	Editing Placemark Details:
Right-click a placemark, select Properties, and update its description.
	•	Toggling Visibility:
Use the checkboxes next to layers or placemarks to show/hide data as needed.
	•	Exporting Data:
Right-click a folder in My Places and select Save Place As to export your changes.
