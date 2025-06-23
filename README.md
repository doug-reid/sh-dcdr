# sh-dcdr:
A tool for general purpose pulse-based communication analysis

## Setup
`npm install && npm link`

## Roadmap
**Vision**: To build a command-line multi-tool for detecting, analyzing and decoding various forms of pulse-based communication from audio, starting with classic Morse code, and evolving towards a generic classification and decoding engine.

**Overall Goal**: Showcase open-source collaboration and SIGINT/EW concepts through beginner-friendly, open-source software development, delivered iteratively.

### Phase 1: Foundation & Core Decoding
**Goal:** Establish a base for audio processing and deliver a functional Morse code decoder for clear signals.

#### Iteration 1: Basic Morse Code Decoding (In Progress)

- [Specify a local audio file as input to the decoder utility](https://github.com/doug-reid/sh-dcdr/issues/2)
- [Process the input audio](https://github.com/doug-reid/sh-dcdr/issues/3)
- [Inform the user if the audio does not contain detectable Morse code](https://github.com/doug-reid/sh-dcdr/issues/4)
- [Inform the user if target file does not exist](https://github.com/doug-reid/sh-dcdr/issues/5)
- [Document basic command-line help](https://github.com/doug-reid/sh-dcdr/issues/6)

**Focus:** Core audio input, pulse detection, and simple Morse character decoding.

**Key Deliverables:** CLI executable capable of decoding clean Morse from .wav files.

**Technical Spikes/Learning:** Audio file parsing, basic FFT/Goertzel for tone detection, timing analysis for dits/dahs.

### Iteration 2: Robustness & Refinement (Morse)

**Focus:** Improving the accuracy and usability of the Morse decoder under less-than-ideal conditions.

**Key Deliverables:** More robust Morse decoder, WPM auto-detection (or a configurable option), improved noise handling, file output.
Technical Spikes/Learning: Advanced signal filtering (bandpass), adaptive thresholding, auto-correlation for WPM estimation, basic error handling in decoding.

### Phase 2: Generic Pulse Analysis & Classification

**Goal:** Extend the utility beyond specific Morse code to identify and characterize unknown pulse-based communication patterns.

#### Iteration 3: Feature Extraction & Visualization

**Focus:** Extracting meaningful features from detected pulses and visualizing them to identify patterns, without assuming a known alphabet.

**Key Deliverables:** Pulse/gap detection engine, feature extraction, basic CLI-based data visualization (or output for external visualization tools), data export.
Technical Spikes/Learning: Advanced transient detection, clustering algorithms (e.g., K-Means for simple grouping of pulse/gap durations), data serialization.

#### Iteration 4: Pattern Recognition & Classification

**Focus:** Implementing algorithms to automatically group and classify pulse patterns, suggesting potential "symbol" sets or communication types.

**Key Deliverables:** Unsupervised clustering of pulse/gap features, sequence pattern detection, auto-generated "alphabet" summaries, ability to load custom decoding rules.

**Technical Spikes/Learning:** More advanced clustering (DBSCAN, GMM), sequence analysis (e.g., Hidden Markov Models (HMM) or simpler state machines), comparison of patterns.
Phase 3: Real-time Analysis & Expansion
Goal: Enable live audio input and integrate with SDRs for real-time analysis, expanding to more complex signal types.

#### Iteration 5: Live Audio Input

**Focus:** Adapting the existing decoding and analysis capabilities to work with live audio streams from the system microphone or virtual audio cables

**Key Deliverables:** Real-time audio capture and processing, continuous output.

**Technical Spikes/Learning:** Audio I/O libraries for real-time streaming, buffering strategies.

#### Iteration 6...N: Further Expansion (e.g., Digital Modes, SDR Integration)

**Focus:** Decoding specific known digital modes from live or recorded audio, or integrating directly with SDR device APIs.

**Key Deliverables:** Decoders for additional digital modes, SDR device API integration, advanced signal classification for interference.

**Technical Spikes/Learning:** Protocol-specific demodulation/decoding, `librtlsdr` bindings (or similar for other SDRs), deeper machine learning for classification.

### General Considerations Across Iterations:

- **Testing:** Implement unit and integration tests for signal processing logic and CLI functionality.
- **Performance:** Monitor CPU/memory usage and optimize as needed, especially with live audio.
- **Documentation:** Keep the README.md updated with features and usage examples.
- **Error Handling:** Continue to improve robustness against unexpected input or signal conditions.
- **Refactoring:** Regularly refactor code to maintain cleanliness and modularity as features grow.
  
