# Module 3: Audio Parser

**Tech Stack:** Python (Librosa + Aubio + OpenAI Whisper)

## Purpose
Comprehensive audio analysis to extract beats (±50ms precision), song structure, lyrics, and mood. Provides creative foundation for all downstream decisions.

## Key Features
- Beat Detection (Librosa + Aubio, 90%+ accuracy within ±50ms)
- Tempo (BPM) extraction (60-200 range)
- Song Structure classification (intro/verse/chorus/bridge/outro)
- Lyrics extraction (OpenAI Whisper API with word-level timestamps)
- Mood classification (energetic, calm, dark, bright)
- Clip Boundaries (beat-aligned, 4-8s clips, minimum 3)
- Caching (Redis cache by audio file hash, 24h TTL)

## Fallback Strategies
- Beat detection fails → Use tempo-based boundaries (4-beat intervals)
- Lyrics fail → Return empty array (instrumental)
- Low confidence → Flag for review, proceed with best-effort

