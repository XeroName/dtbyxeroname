# Documination of Deltatime
This documination is unfinished yet.

# Introduction
"Deltatime"(aka DtbX) is a TurboWarp extension which provides soft, precision Delta timing blocks.

# Important notice
- Note that FPS and ΔT are in directly-impactable relationship, so even mentioning only "FPS" or "ΔT" mostly means both of them.
- ΔT means the "Delta Time".

# FPS & ΔT
FPS and ΔT value of DtbX has following properties :
- **FPS** block returns roundary integer value of current Framerate using `Math.round()`.
- When Framerate goes down to < 0.5, **FPS** block starts to return real number by 2 decimal places using `toFixed()`.
- If the **FPS** value is not grater than 0, **ΔT** value will be also 0 until FPS grater than 0.

# "Filtering" Blocks
**Filtering** blocks are purposed to stablize FPS, and **Filter Strength**(aka strength) directly determines the performance of ΔT.

When filter strength has been set to higher value :
- FPS and ΔT will be less fluctuate.
- Updating time of FPS and ΔT will be increase. That means small variation of FPS may be ignored as strength arises.

# Stability Evaluator
Stability Evaluator provides value of "How much stable FPS is" in actual working.
Not added yet.
