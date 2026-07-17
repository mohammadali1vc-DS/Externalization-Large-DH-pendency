
# Data Sources & Download Links

This file contains the source links used to download input data for the Externalization Large DH Pendency report processing.

## Data Sources

### 1. MPS Forward Report Portal
- **URL:** http://10.24.42.15/Mps_Forward_Report/
- **Description:** Internal portal serving daily MPS (Multi-Piece Shipment) forward report files for large category shipments.
- **File Format:** `mps_forward_report_YYYY-Mon-DD_HH_MM_SS.csv.gz`
- **File Size:** ~30–40 MB per file (compressed)
- **Update Frequency:** Every 3 hours daily
- **Target File:** File with `09_20` timestamp is used as the primary daily data source
- **How to Use:** The Python script auto-connects, detects today's date, downloads and extracts the correct `.csv.gz` file automatically

### 2. FDP Report (Ext_large_bulk_raw)
- **URL:** https://fdp.fkinternal.com/reports/view/scp/ekl/Ext_large_bulk_raw
- **Description:** Raw bulk shipment data for large category orders from the FDP (Flipkart Data Platform) portal.
- **Recommended Date Filter:** Last 3 Months + Current Month (or custom range)
- **Applied Filters:**
  - `vendor_code`: FSD_LARGE, FSD_LARGE_COD
  - `merchant_code`: not in (FKMP, MLA)
  - `ekl_shipment_type`: Forward, RTO, RVP
- **How to Use:** Apply filters → Refresh Report → Download CSV

## Notes
- Both portals are **internal** and require authorized Flipkart network access.
- MPS Forward Report is the **primary data source** for the DH Pendency script.
- FDP data is used for **cross-verification** and enrichment of shipment details.
- Always use today's `09_20` timestamp file from MPS portal for accurate daily pendency.
