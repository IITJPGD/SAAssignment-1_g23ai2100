# SAAssignment-1_g23ai2100_g23ai2066

Stream Analytics  
Assignment – 1

g23ai2100

g23ai2066


# Network Traffic Analysis Using SiLK Suite

A tool for analyzing and classifying network traffic patterns using the SiLK Suite. 
This project include 
TCP traffic analysis
node classification
anomaly detection.

## Prerequisites

- SiLK Suite
- Python 3.x with pandas and matplotlib

## Quick Start

1. **silk Setup**
   ```
   gzip -d -c FCCX-silk.tar.gz | tar xf -
   cd FCCX-silk
   export SILK_DATA_ROOTDIR=$(pwd)
   ```

2. **TCP Traffic Analysis**
   ```
   # Filter TCP traffic
   rwfilter --proto=6 --type=in,inweb,out,outweb \
           --start-date=2015/06/02T13 --end-date=2015/06/18T18 \
           --pass-destination=tcp_traffic.rw

   # Generate summary and CSV
   rwstats tcp_traffic.rw --fields=sip,dip --count=10
   rwcut --fields=sip,dip,packets,stime --no-titles --output-path=tcp_data.csv tcp_traffic.rw
   ```

3. **Node Classification**
   - Run the provided Python Jupiter Notebook script to:
     - Classify nodes based on traffic volume (Low/Medium/High) 
     - Generate visualization plots
     - Save classified data to CSV

## Output Files

- `tcp_traffic.rw`: Filtered TCP traffic data
- `raw/data.csv`: Raw TCP flow data
- `classified_data.csv`: Node classification results

## Visual traffic distribution

## Data Source

Dataset: `FCCX-silk.tar.gz` from CERT NetSA Security Suite reference data page.