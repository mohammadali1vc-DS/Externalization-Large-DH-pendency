
# Externalization Large DH Pendency

This repository contains the Python (Jupyter Notebook) script to process and report **Large Forward DH (Dispatch Hub) Pendency** — covering Zero Attempt and NDR shipments for large category orders.

## What This Script Does

1. **Auto-Downloads Daily MPS Forward Report**
   - Connects to the internal MPS portal (`10.24.42.15/Mps_Forward_Report/`)
   - Automatically detects today's date and downloads the correct `.csv.gz` file (09:20 timestamp)
   - Extracts and loads it into a pandas DataFrame

2. **Processes Pendency Data**
   - Filters large forward shipments with pending delivery
   - Analyzes Zero Attempt and NDR (Non-Delivery Report) cases
   - Tracks shipment fields: ShipmentId, CurrentHub, OriginHub, DestinationHub, ShipmentCategory, OBDType, PriorityScore, and more

3. **Generates Pivot Reports**
   - Table 1: GM vs Remark breakdown
   - Table 2: State vs Remark breakdown
   - Table 3: Remark vs LPD breakdown
   - Table 4: Total Volume by Remark
   - Table 5: Total Volume by Zone

4. **Exports Excel Report**
   - Output file: `Large FWD Pendency <date>.xlsx`

5. **Sends Automated Email**
   - Sends HTML-formatted email with pivot tables and Excel attachment
   - Subject: `Externalization Large DH pendency, Zero Attempt + NDR of <date>`
   - Distributed to GMs, LH teams, LM ops, and client communication teams across all zones (North, South, East, West, Central)

## Requirements

- Python 3
- Jupyter Notebook / JupyterLab
- Libraries: `pandas`, `requests`, `beautifulsoup4`, `openpyxl`, `smtplib`

## Usage

1. Open the `.ipynb` file in JupyterLab.
2. Run all cells sequentially.
3. The script will auto-download today's data, process it, generate the Excel report, and send the email automatically.

## Data Source

- **MPS Forward Report Portal:** `http://10.24.42.15/Mps_Forward_Report/`
- File format: `mps_forward_report_YYYY-Mon-DD_09_20_XX.csv.gz`
