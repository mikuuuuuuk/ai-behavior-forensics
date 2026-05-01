# ai-behavior-forensics
A browser-based forensic typing analysis framework to distinguish genuine human cognition from AI-assisted transcription.




# ThoughtTrace Pro 

[![Version](https://img.shields.io/badge/version-2.8.0-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)]()
[![Platform](https://img.shields.io/badge/platform-Browser-lightgrey.svg)]()

> *Read this in [繁體中文](README_zh-TW.md) | [简体中文](README_zh-CN.md)*

*ThoughtTrace Pro** is a browser-based forensic typing analysis framework designed to distinguish genuine human cognition from AI-assisted transcription. 

Unlike traditional NLP-based AI detectors (which analyze the *final text*), ThoughtTrace analyzes the **behavioral biometrics** of the *writing process*.

#  The Problem
Current AI detection tools fail when users manually transcribe AI-generated text or perform heavy "AI-assisted editing." They also struggle with false positives, accusing genuine students of cheating.

#  The Solution: Behavioral Biometrics
ThoughtTrace monitors keystroke dynamics, context switching, and input entropy to create a Session Audit Trail. It doesn't judge the words; it judges *how* the words were typed.

#  Core Engines
*   Baseline Calibration: Establishes a personalized typing fingerprint (Jitter/CV) before the session begins to prevent device bias.
*   Sync Coverage Algorithm: Compares DOM text length with actual keystroke events. Instantly flags massive clipboard injections (Copy-Paste).
*   Cognitive Entropy (CV) Analysis: Analyzes the Coefficient of Variation (CV) of keystroke delays. Authentic human thought produces non-linear, rhythmic jitter. Manual transcription of AI text produces mechanical, linear input.
*   Focus Loss Tracking: Monitors tab-switching and window blur events to detect "Synthesizer" behavior (reading from an external AI window).

#  Quick Start
This is a zero-dependency, local-first vanilla JavaScript prototype.
1. Clone the repository.
2. Open `index.html` in any modern browser.
3. Complete the Initial Calibration to unlock the secure buffer.

# Privacy First
**100% Local Processing.** ThoughtTrace Pro relies on `localStorage` and client-side processing. No keystroke data or written content is ever sent to a remote server. 

# Final Output
Generates a downloadable PDF Forensic Audit Report containing a timeline of behavioral shifts (e.g., `[CRITICAL_PASTE]` followed by `[HUMAN_RECOVERY]`), providing educators with context rather than just a binary score.
