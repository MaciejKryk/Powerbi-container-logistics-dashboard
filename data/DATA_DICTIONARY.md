# Dataset: Container Logistics (synthetic)

This dataset is **synthetic** (generated) and safe to publish.

## Files
- `dim_calendar.csv` – Date table (2024-01-01 to 2025-12-31)
- `dim_customers.csv` – Customers
- `dim_products.csv` – Products shipped inside containers
- `dim_carriers.csv` – Shipping lines / carriers
- `dim_ports.csv` – Origin & destination ports
- `fact_shipments.csv` – One row per shipment (cost, revenue, delay, TEU)
- `fact_shipment_lines.csv` – Products per shipment (lines)

## Keys & relationships (recommended)
- `fact_shipments[CustomerID]` → `dim_customers[CustomerID]`
- `fact_shipments[CarrierID]` → `dim_carriers[CarrierID]`
- `fact_shipments[OriginPortID]` → `dim_ports[PortID]`
- `fact_shipments[DestPortID]` → `dim_ports[PortID]`
- `fact_shipments[BookingDate]` → `dim_calendar[Date]`
- `fact_shipment_lines[ShipmentID]` → `fact_shipments[ShipmentID]`
- `fact_shipment_lines[ProductID]` → `dim_products[ProductID]`

## Business questions you can answer
- OTIF / on-time performance by carrier, port, trade lane
- Profitability by customer segment & trade lane
- Cost drivers (freight vs surcharge vs inland vs handling)
- Delay reasons & their impact on profit and lead time
