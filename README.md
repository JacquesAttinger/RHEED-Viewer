# RHEED (Reflection High-Energy Electron Diffraction) Viewer

RHEED Viewer is a Graphical User Interface (GUI) application for acquiring, displaying, and saving Reflection High-Energy Electron Diffraction (RHEED) data in real-time. It includes a RHEED imaging live stream (including RHEED oscillations), as well as the ability to acquire single images or streams of images at a specified frequency and duration, making it useful for acquiring thin-film growth trajectory data. Integration with a BASF pyrometer enables users to cross-correlate temperature data with the RHEED images. While proprietary RHEED softwares offer more advanced features, this software offers greater personalization for integration with custom data processing pipelines.

## Features

- **Live RHEED Feed**: View real-time RHEED patterns with adjustable exposure and frame rates.
- **Intensity Oscillations**: Select a rectangular Region of Interest (ROI) on the live feed to plot intensity oscillations in real-time.
- **Image Acquisition**:
  - **Single Capture**: Save individual RHEED frames.
  - **Streaming**: Record sequences of frames at a specified frequency and duration (useful for saving thin-film growthtrajectory data).
- **Metadata Integration**: Automatically embeds temperature readings (from a connected pyrometer) and timestamps into filenames.

## Hardware Requirements

- **Camera**: Allied Vision camera (uses `vmbpy` driver).
- **Pyrometer**: Uses the BASF EXACTUS pyrometer.

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
- `environment.yml`: Conda environment definition.

