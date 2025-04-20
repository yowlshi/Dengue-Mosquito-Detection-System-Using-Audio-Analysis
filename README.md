# Dengue Mosquito Detection System Using Audio Analysis

## Overview
This project implements an audio analysis system for detecting the presence of dengue-carrying mosquitoes (Aedes aegypti) based on their distinctive wingbeat frequency. The system processes audio recordings and identifies if the frequency patterns match those characteristic of dengue vectors.

## The Problem
Dengue fever remains a significant public health issue in the Philippines, with over 208,000 cases reported as of September 2024, exacerbated by favorable breeding conditions from climate change. Research shows that the wingbeat frequency of Aedes aegypti, the primary dengue vector, typically ranges between 300–600 Hz, making this frequency band critical for distinguishing it from other insects and environmental sounds.

## Features
- Supports both WAV and MP3 audio file formats
- Processes audio to isolate frequencies in the 300-600 Hz range
- Visualizes audio data through time-domain signals and spectrograms
- Performs Fast Fourier Transform (FFT) to identify dominant frequencies
- Alerts when mosquito wingbeat frequencies are detected

## Technical Details

### Dependencies
- NumPy: For numerical operations, array manipulations, and Fourier Transform
- Matplotlib: For plotting time-domain signals and spectrograms
- SciPy: For signal processing tasks like filtering, peak finding, and spectrogram calculation
- Pydub: To handle MP3 files and convert them to a format suitable for processing

### System Architecture
1. **Audio Loading**: Handles WAV and MP3 formats, converting stereo to mono when necessary
2. **Preprocessing**: 
   - Normalizes audio amplitude to the range [-1, 1]
   - Applies a bandpass filter (300-600 Hz) to isolate potential mosquito frequencies
3. **Analysis**:
   - Computes spectrograms to visualize frequency distribution over time
   - Performs FFT to identify dominant frequency components
4. **Detection**:
   - Identifies peak frequencies using the `find_peaks` function
   - Compares detected frequencies against the known dengue mosquito frequency range

## Usage
1. Run the main script
2. Upload your audio file (WAV or MP3)
3. The system will process the file and output:
   - Audio playback capability
   - Visualization of the audio spectrum
   - Detection results and dominant frequencies
   - Alert if dengue mosquito frequencies are detected

## Implementation Details
The system uses a band-pass filter to isolate the frequency range of interest (300-600 Hz). The Fast Fourier Transform (FFT) converts the time-domain signal to the frequency domain, allowing the system to identify the dominant frequencies present in the audio.

Key formulas:
- Frequency resolution: Δf = sample_rate / length of audio
- Peak detection uses a minimum height threshold of 0.1 * maximum magnitude

## Limitations and Disclaimer
**Note:** This program is a proof-of-concept and has several limitations:

1. The detection is based solely on wingbeat frequency and may generate false positives from other insects or sounds in the same frequency range
2. Environmental noise can significantly impact detection accuracy
3. The system requires relatively clean audio recordings with minimal background noise
4. No machine learning components are implemented for pattern recognition or species classification
5. The current implementation is for demonstration purposes and would need substantial refinement for real-world applications

This project demonstrates how audio analysis could potentially be used for mosquito detection, but should not be relied upon for actual public health interventions without further development and validation.

## Future Improvements
- Implement machine learning algorithms to improve classification accuracy
- Add spectrum pattern matching beyond simple frequency detection
- Include mobile application interface for field usage
- Integrate with IoT devices for continuous monitoring
- Expand the database of mosquito species and their characteristic frequencies

## Repository
Source code: [https://github.com/yowlshi/Dengue-Mosquito-Detection-System-Using-Audio-Analysis](https://github.com/yowlshi/Dengue-Mosquito-Detection-System-Using-Audio-Analysis)

## References
- Cator et al., 2009: Research on wingbeat frequency ranges of Aedes aegypti
- ABS-CBN News: Dengue fever statistics in the Philippines (September 2024)
