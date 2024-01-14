# Voice Anonymization App

## Overview
This project aims to develop an Android/iOS application that modifies a user's voice in real-time during phone calls to protect against voice cloning and unauthorized recording. The application will alter the voice in a way that it sounds normal to humans but different to computers, thereby preventing misuse of voice-protected services like banking and mobile access.

## Techniques Used
The application employs two primary voice anonymization techniques:
1. **Pitch Scaling**: Modifies the pitch of the voice by a specified number of semitones, within the range of [-11, 11].
2. **Vocal Tract Length Normalization (VTLN)**: Alters the frequency spectrum of the voice using various warping functions (bilinear, quadratic, power, piecewise-linear). Parameters for these functions are as follows:
   - Bilinear: α ∈ [-0.3, 0.3] with a step of 0.02
   - Quadratic: α ∈ [-2, 2] with a step of 0.2
   - Power: α ∈ [-0.5, 0.5] with a step of 0.05
   - Piecewise-linear: α ∈ [0.5, 1.5] with a step of 0.05

## Development Approach
The development process involves:
- Capturing audio in real-time from the device's microphone.
- Applying the selected voice anonymization techniques to the audio stream.
- Testing and validating the effectiveness of these techniques against voice recognition systems.
- Ensuring the modified voice maintains intelligibility and quality for human listeners.

## Technical Stack
- **Language**: Python (for prototype and algorithm development).
- **Libraries**: `librosa` (for audio processing), `numpy` (for numerical operations), `pyaudio` (for audio capture).
- **Platform**: Targeting Android and iOS for the final application. Initial development and testing are done in a Python environment.

## Future Work
- Integration of the voice anonymization algorithms into a mobile application framework.
- Optimization for real-time processing with minimal latency.
- User interface development for easy interaction and control of anonymization parameters.
- Extensive testing on various devices and environments.
- Security measures to protect the anonymity of users.

## Notes
- This project is in the prototyping phase, focusing on developing and testing the core voice anonymization algorithms.
- The choice of pitch scaling and VTLN techniques is based on their effectiveness and feasibility for real-time processing.
- Further research and development are needed to refine these techniques and counteract advanced speaker de-anonymization methods.

## Sources of interest
- Inspiration https://dl.acm.org/doi/10.1145/3576915.3616616
- Test vocals with https://github.com/kaldi-asr/kaldi
- VSTM algos https://github.com/DenisStad/Voice-Conversion
