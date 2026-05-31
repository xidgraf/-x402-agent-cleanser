# x402 Agent Cleansing Engine (Base Network TEE)

An autonomous, stateless, and network-isolated Machine-to-Machine (M2M) mathematical processing engine engineered specifically for **x402 category agents**. 

This asset executes strictly within decentralized Trusted Execution Environments (TEEs) via Ocean Protocol Compute-to-Data on the **Base Network**. It allows x402 agents to eliminate accumulated data weight, baseline structural drift, and hallucinated payload anomalies through pure, deterministic mathematical recalibration—settled programmatically via pay-per-parse stablecoins (USDC/EURC).

## ⚡ x402 Operational Specifications

* **Pure M2M / Zero-Human Boundary**: Functions completely without web API frameworks, network sockets, or external port listening. 
* **Hardened Temporal Isolation**: Strict mathematical decoupling from system hardware clocks (NTP/PTP) and underlying Gregorian calendars to guarantee host environment integrity.
* **Deterministic Recalibration**: Implements immutable vector copies to process hardware and software variables, ensuring zero state mutation or environmental pollution.

## 📂 Repository File Structure

```text
└── README.md     --> Architectural Blueprint and JSON Payload Schemas
```

---

## 🛰️ Machine-to-Machine Integration Blueprint

To utilize this asset on the Ocean Market, your parent agent framework (e.g., Autonolas, Coinbase AgentKit) must mount input matrices onto the localized `/data/inputs/` volume.

### 📥 1. Ingestion Schema (`/data/inputs/coordinates.json`)
The script processes dual-matrix arrays simultaneously. Pass your raw tracking telemetry and structural values structured exactly as follows:

```json
{
    "nodal_data": [
        {
            "julian_day": 2461180.5,
            "body": "moon",
            "longitude_deg": 45.200000,
            "latitude_deg": 0.500000,
            "anomaly_deg": 12.000000
        },
        {
            "julian_day": 2461180.5,
            "body": "jupiter",
            "longitude_deg": 120.800000,
            "latitude_deg": -1.100000,
            "anomaly_deg": 84.500000
        }
    ],
    "pyramid_data": {
        "base_length": 230.34
    }
}
```

### 📤 2. Egress Schema (`/data/outputs/cleansed_parameters.json`)
Upon completion, the engine exports a synchronized payload back to the local TEE volume. Your listening agent reads the `m2m_accounting` block to verify data unit throughput and trigger automated billing cycles.

```json
{
    "status": "synchronized",
    "m2m_accounting": {
        "total_rows_parsed": 3,
        "nodal_rows": 2,
        "pyramid_units": 1
    },
    "nodal_output": [
        {
            "julian_day": 2461180.5,
            "body": "moon",
            "longitude_sexagesimal": "45°; 12'; 00.00''",
            "zodiac_sign": "Taurus (MUL.MUL)",
            "zodiac_position_deg": 15.2,
            "synodic_arc_deg": 29.530589,
            "anomaly_correction_deg": 0.464912,
            "nodal_distance_deg": 178.504212,
            "eclipse_risk_flag": 0,
            "saros_number": 152,
            "goal_year_period": 18.6116,
            "predicted_longitude_deg": 75.195501
        }
    ],
    "pyramid_output": {
        "pi_geometric_approx": 3.142857,
        "phi_golden_ratio": 1.618033,
        "phi_seked_delta": 0.000729,
        "face_slope_angle_deg": 51.842773,
        "scaled_height": 146.579998,
        "scaled_apothem": 186.368541,
        "scaled_lateral_area": 77931.428514,
        "scaled_volume": 2595058.125412
    }
}
```

---

## 🛠️ Local Verification Workflow

To test the container ecosystem locally before committing your immutable image hash (`sha256`) to the Base network registry, execute the following commands in sequence:

```bash
# 1. Initialize local test volume mounts
mkdir -p data/inputs data/outputs

# 2. Stage your test payload
cp test_coordinates.json data/inputs/coordinates.json

# 3. Build the isolated x402 execution layer
docker build -t x402-agent-cleanser:latest .

# 4. Run the stateless simulation loop
docker run --rm \
  -v \$(pwd)/data/inputs:/data/inputs \
  -v \$(pwd)/data/outputs:/data/outputs \
  x402-agent-cleanser:latest

# 5. Verify the synchronized data output
cat data/outputs/cleansed_parameters.json
```

## 🔒 Security Matrix
* **Network Capabilities**: Disallowed (`allowNetworkAccess: false` within Ocean DDO metadata).
* **Process Privileges**: Runs strictly under UID `8888` (`appuser`). Root isolation enforced.
* **Storage Footprint**: Ephemeral state storage. Container memory is instantly wiped post-execution.
