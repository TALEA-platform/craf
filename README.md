<h1> 🌿 Climatic Fragility and Resilience Analysis</h1>

<p>
This repository contains data processing scripts and analysis notebooks developed within the 
<strong>TALIA (Green Cells Leading the Green Transition)</strong> project.
It contributes to the ongoing <strong>Climate Shelters 2025</strong> initiative focused on assessing 
<strong>urban climatic fragility</strong> and supporting <strong>climate-resilient urban planning</strong> 
in the Bologna metropolitan area.
</p>

<hr>

<h2>🧭 Topic</h2>
<p>
The project integrates <strong>thermal, land-cover, morphological, and socio-environmental datasets</strong> 
to identify <strong>urban areas vulnerable to heat exposure</strong> and to support the implementation of 
<strong>nature-based solutions</strong>.
</p>

<p>
The methodological reference for this work is:<br>
<blockquote>
<b>Investigating Social Vulnerability to Extreme Heat: Heat Islands and Climate Shelters in Urban Contexts: The Case of Bologna</b><br>
<em>International Journal of Geo-Information (2024)</em><br>
<a href="https://tustorage.ulb.tu-darmstadt.de/server/api/core/bitstreams/5655dda2-e4a6-47c5-861a-4aa6102fe31d/content" target="_blank">
📄 Read the full paper here
</a>
</blockquote>
</p>

<hr>

<h2>📁 Folder Structure</h2>

<pre>
climate-shelter/
│
├── source/                      # Jupyter notebooks for analysis modules
│   ├── 01_LST_processing.ipynb   # ECOSTRESS LST preprocessing & classification
│   ├── 02_zonal_stats.ipynb      # Hot/cold % computation per area
│   ├── 03_fragility_index.ipynb  # Climatic fragility computation
│   ├── Accessibility.ipynb       # Accessibility and structure integration
│   ├── new_CSI.ipynb             # CSI computation
│   ├── Climatic_fragility.ipynb  # Integration of all indicators
│   ├── Fragility.ipynb           # Final composite fragility index
│   └── ...
│
├── data/                        # Input + processed data (linked externally)
│   ├── Climatic_fragility/
│   ├── Meteoblue/
│   └── ...
│
├── requirements.txt             # Python dependencies
└── README.md                    # Repository overview
</pre>

<hr>

<h2> Data Sources</h2>

<table>
<thead>
<tr>
<th>Category</th>
<th>Data Source</th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Thermal</strong></td>
<td>ECOSTRESS LST (NASA JPL)</td>
<td>Hot and cold spot classification</td>
</tr>
<tr>
<td><strong>Land Cover</strong></td>
<td>Sentinel-2, Copernicus Urban Atlas</td>
<td>Green/blue area extraction</td>
</tr>
<tr>
<td><strong>Topography</strong></td>
<td>Copernicus DEM</td>
<td>Slope and terrain context</td>
</tr>
<tr>
<td><strong>Socio-Environmental</strong></td>
<td>ISTAT Census, Climate Shelter Index (CSI)</td>
<td>Sensitivity and adaptation capacity</td>
</tr>
<tr>
<td><strong>Administrative</strong></td>
<td>Comune di Bologna Statistical Areas</td>
<td>Zonal unit for analysis</td>
</tr>
<tr>
<td><strong>Meteorological</strong></td>
<td>Meteoblue, ERA5 Reanalysis</td>
<td>Validation of LST patterns</td>
</tr>
</tbody>
</table>

<p>
🔗 Large raster and shapefile datasets are stored in 
<a href="https://drive.google.com/drive/folders/16NpHEfSyUm6AXLdMhPH9fCHvgtomCzRF?usp=drive_link" target="_blank">
Google Drive
</a>.
</p>

<hr>

<h2>🧮 Execution Workflow</h2>

<p>
The analysis for <strong>TALIA – Climate Shelters 2025</strong> follows a sequential execution of Jupyter Notebooks.
Each step processes or integrates a thematic dataset (thermal, vegetation, structures, accessibility, etc.) leading to the
final <strong>Climatic Fragility Index</strong>.
</p>

<h3>📘 Processing Chain</h3>

<pre>
Clip / Resample rasters → Hot_and_Cold_Spot
           ↓
Calculate NDVI → NDVI_for_CSI
           ↓
Structures + Accessibility + Area → Identify_structures_for_CSI + Accessibility + others
           ↓
Combine into CSI → new_CSI.ipynb
           ↓
Combine all into HF → Climatic_fragility.ipynb
           ↓
Final index → Fragility.ipynb
</pre>

<h3>📔 Notebook Execution Order</h3>

<ol>
  <li>Clip_gdal.ipynb</li>
  <li>Resampling.ipynb</li>
  <li>Hot_and_Cold_Spot.ipynb</li>
  <li>NDVI_for_CSI.ipynb</li>
  <li>bus_stop.ipynb</li>
  <li>Disabled_parking.ipynb</li>
  <li>Accessibility.ipynb</li>
  <li>Identify_structures_for_CSI.ipynb</li>
  <li>new_CSI.ipynb</li>
  <li>Climatic_fragility.ipynb</li>
  <li>Fragility.ipynb</li>
</ol>

<p>
Each notebook builds on the outputs of the previous one — moving from <strong>exposure analysis (thermal)</strong>,
to <strong>adaptation capacity (CSI)</strong>, and finally to <strong>composite climatic fragility mapping</strong>.
</p>

<hr>

<h2>📊 Fragility Index Summary (Bologna)</h2>

<p>
The <strong>Climatic Fragility Index (CFI)</strong> for Bologna statistical areas ranges approximately between 
<code>0.0</code> and <code>1.0</code>, where higher values indicate increased urban vulnerability to heat exposure.
</p>

<table>
<thead>
<tr>
<th>Fragility Range</th>
<th>Fragility Level</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td><b>0.00 – 0.25</b></td>
<td>Very Low</td>
<td>Areas with high vegetation, strong accessibility, and cooling infrastructure</td>
</tr>
<tr>
<td><b>0.26 – 0.45</b></td>
<td>Low</td>
<td>Moderate resilience with balanced exposure and adaptation</td>
</tr>
<tr>
<td><b>0.46 – 0.60</b></td>
<td>Moderate</td>
<td>Intermediate fragility, partial vegetation or exposure mitigation</td>
</tr>
<tr>
<td><b>0.61 – 0.75</b></td>
<td>High</td>
<td>High exposure to heat stress with limited green/blue adaptive capacity</td>
</tr>
<tr>
<td><b>0.76 – 1.00</b></td>
<td>Very High</td>
<td>Urban cores and industrial zones with significant vulnerability</td>
</tr>
</tbody>
</table>

<h3>📈 Observed Values in Bologna</h3>

<p>
From the calculated areas, <strong>TRIUMVIRATO–PIETRA</strong> and <strong>CASTELDEBOLE</strong> recorded 
moderate fragility (~0.50), while <strong>PIAZZA DELL’UNITÀ</strong> and <strong>VILLAGGIO DELLA BARCA</strong>
showed the highest fragility values (~0.65–0.70).  
In contrast, <strong>OSSERVANZA</strong> and <strong>SAN MICHELE IN BOSCO</strong> demonstrated 
very low fragility (<0.30) due to their high vegetation and environmental resilience.
</p>

<p>
Overall, the <strong>new fragility index</strong> after integrating LST-based exposure improved the spatial sensitivity
of results, providing a refined fragility range of approximately:
</p>

<p style="text-align:center; font-weight:bold; font-size: 1.1em;">
0.18 ≤ Fragility ≤ 0.81
</p>

<p>
This indicates that Bologna’s climatic fragility spans from <strong>very resilient green districts</strong> 
to <strong>highly vulnerable dense urban zones</strong>.
</p>

<hr>

<h2>🧱 Tasks Completed</h2>
<ul>
<li>✅ ECOSTRESS LST classification and validation</li>
<li>✅ Hot/cold area statistics integration</li>
<li>✅ NDVI and accessibility layer integration</li>
<li>✅ CSI and composite climatic fragility computation for Bologna</li>
<li>✅ Correlation analysis with CSI, green%, and blue% </li>
<li>🔜 Integration into TALIA’s resilience mapping framework</li>
</ul>

<hr>

<h2>⚙️ How to Use</h2>

<ol>
<li>
Clone this repository:<br>
<pre><code>git clone https://github.com/username/climate-shelter.git
cd climate-shelter</code></pre>
</li>
<li>
Install dependencies:<br>
<pre><code>pip install -r requirements.txt</code></pre>
</li>
<li>Open JupyterLab or VS Code and run the notebooks inside <code>source/</code>.</li>
<li>Results are exported as GeoPackages and shapefiles in <code>/data/Climatic_fragility/outputs/</code>.</li>
</ol>

<hr>

<h2>📍 Example Area</h2>
<p><strong>Bologna, Italy</strong> – pilot city for validation of climatic fragility mapping.</p>

<hr>

<h2>🧩 Project Status</h2>
<p><strong>Ongoing (2025)</strong> – the analysis will keep updating.</p>

<hr>


