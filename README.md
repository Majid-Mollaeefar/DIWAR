# Digital Identity Wallet Risk Assessment Tool (DIWAR)

> This repository contains the source code of the DIWAR tool, which is described in our paper "Entity-based Risk Assessment: A European Digital Identity Wallet Use Case" submitted to the 30th Nordic Conference on Secure IT Systems.

<!-- A Streamlit-based application for evaluating and calculating risks associated with different entities in the context of Digital Identity Wallets. This tool helps assess threats and implement mitigation controls for various stakeholders in the digital identity ecosystem. -->

## Prerequisites

- Python 3.x
- Dependencies listed in requirements.txt

## Installation

1. Clone the repository

2. Create a virtual environment (recommended):

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
```

3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Project Structure

```plaintext
diwar/
├── .files/               # Configuration and data files
│   ├── threats_controls.json         # Mapping of threats to controls
│   ├── controls_mitigations.json     # Control implementation levels
│   ├── controls_dread.json          # DREAD scoring for controls
│   └── role_threats.json            # Role-specific threat mappings
├── config.py            # Application configuration
├── risk.py             # Main application logic
├── requirements.txt     # Project dependencies
├── icon.png            # Application icon
└── logo.png            # Application logo
```

## Usage

1. Run the Streamlit application:

```bash
streamlit run risk.py
```

2. Navigate the interface:
   - **Risk Assessment Tab**: Evaluate risks for specific entities
   - **Security Control View Tab**: View controls and implementation requirements

3. Perform Risk Assessment:
   - Select an entity (Issuer, Verifier, Wallet Provider, Holder)
   - Review associated threats
   - Set implementation levels for security controls
   - Generate and view risk assessment results

## Control Implementation Levels

The following levels can be set for each control:

- **N/A**: Not applicable
- **Basic**: Fundamental implementation
- **Intermediate**: Enhanced implementation
- **Advanced**: Comprehensive implementation
- **Yes**: For binary controls (implemented/not implemented)

## Risk Assessment Process

1. **Entity Selection**: Choose the stakeholder role to assess
2. **Control Evaluation**: Set implementation levels for each control
3. **Risk Calculation**: System calculates:
   - Impact and likelihood scores
   - Qualitative risk levels
   - Control effectiveness

## Risk Matrix

The tool uses a qualitative risk matrix with the following levels:

- Very Low (Green)
- Low (Yellow)
- Medium (Brown)
- High (Light Red)
- Critical (Dark Red)
