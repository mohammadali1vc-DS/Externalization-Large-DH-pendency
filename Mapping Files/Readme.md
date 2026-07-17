
# Mapping Files

This folder contains the reference and mapping files used by the Python scripts to process the Externalization Large DH Pendency report.

## Files

- **Brands sheet (1).xlsx** — Contains brand-wise classification of large shipment merchants/sellers used for filtering and grouping in the pendency report.

- **Large XD mapping.xlsx** — Maps large shipment XD (cross-dock) hub names for normalizing current location data across Satellite Hubs, Bulk Hubs, and Pickup Hubs.

- **Large_mapping_1.xlsx** — Contains additional merchant or hub-level mapping used for enriching shipment data during processing.

## Purpose

These mapping files are loaded by the Python script to:
- Normalize hub and location names
- Map merchant codes to brands and categories
- Enrich shipment records with correct zone, hub, and seller information

## Notes

- These files must be placed in the working directory before running the Python script.
- Update mapping files periodically to reflect new hubs or merchant onboarding.
