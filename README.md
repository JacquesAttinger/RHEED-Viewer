# RHEED Viewer & Control

A Python-based GUI application for acquiring, viewing, and analyzing Reflection High-Energy Electron Diffraction (RHEED) data in real-time. Designed for Molecular Beam Epitaxy (MBE) systems, this tool interfaces with Allied Vision cameras and pyrometers to monitor thin film growth.

## Features

- **Live RHEED Feed**: View real-time RHEED patterns with adjustable exposure and frame rates.
- **Intensity Monitoring**: Select a Region of Interest (ROI) on the live feed to plot intensity oscillations in real-time, essential for monitoring layer-by-layer growth.
- **Image Acquisition**:
  - **Single Capture**: Save individual RHEED frames.
  - **Streaming**: Record sequences of frames at a specified frequency and duration.
- **Metadata Integration**: Automatically embeds temperature readings (from a connected pyrometer) and timestamps into filenames.
- **Data Analysis**: Tools for analyzing RHEED oscillations (see `GetOscillationPlot.py`).
- **Dual System Support**: Includes configurations for both Calcogenide and Oxide MBE systems.

## Hardware Requirements

- **Camera**: Allied Vision camera (uses `vmbpy` driver).
- **Pyrometer**: Compatible pyrometer for temperature reading (see `PyrometerControl.py`).

## Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd RHEED-Viewer
   ```

2. **Set up the environment**:
   This project uses a Conda environment. You can create it using the provided `environment.yml` file.
   ```bash
   conda env create -f environment.yml
   conda activate py311
   ```

3. **Install Drivers**:
   Ensure the Vimba X drivers for Allied Vision cameras are installed on your system.

## Usage

To launch the GUI for the Calcogenide MBE system:

```bash
python Code/CalcogenideMBE_Rheed_GUI.py
```

For the Oxide MBE system:

```bash
python Code/OxideMBE_Rheed_GUI.py
```

### Workflow
1. **Start Live Feed**: Click to begin viewing the camera stream.
2. **Oscillation Settings**: Define a region of interest (ROI) to track intensity changes.
3. **Acquire/Stream**:
   - Use "Acquire RHEED Image" for a snapshot.
   - Use "Start RHEED Stream" to record a sequence. You will be prompted to enter parameters like duration, frequency, and grower initials.

## Project Structure

- `Code/`: Source code for the application.
  - `CalcogenideMBE_Rheed_GUI.py`: Main entry point for Calcogenide MBE.
  - `OxideMBE_Rheed_GUI.py`: Main entry point for Oxide MBE.
  - `PyrometerControl.py`: Interface for pyrometer communication.
  - `GetOscillationPlot.py`: Utilities for plotting and analyzing oscillations.
- `environment.yml`: Conda environment definition.

## License

[Insert License Information Here]
