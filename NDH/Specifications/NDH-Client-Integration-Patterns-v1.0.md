### NDH Client Integration Patterns v1.0  
*How NDH plugs cleanly into Unity, Unreal, Godot, XR, audio, and the accessibility stack.*

---

## 1. Core pattern (engine‑agnostic)

All engines follow the same basic pattern:

1. **Call NDH API** → fetch manifold state  
2. **Map NDH structures to engine primitives**  
3. **Apply accessibility profile + sensory mode**  
4. **Render / play / vibrate**  
5. **Log via JDTR**  
6. **Respect HRD constraints**

Key NDH structures:

- **GeometryEnvelope** → spatial layout  
- **Basins / Corridors / Margins** → regions, paths, boundaries  
- **Tensors** → forces, stress, resonance, visual/audio/haptic cues  
- **Modes** → Calm/Serenity/Tranquility/Peace/Dark/Normal  
- **Accessibility fields** → profile, sensoryMode, cognitiveEase  
- **AudioField / HapticField** → direct sensory mapping  

---

## 2. Unity integration pattern

**Mapping:**

- **GeometryEnvelope** → Scene graph (GameObjects, transforms)  
- **Basins** → volumes (colliders, zones)  
- **Corridors** → paths (splines, navmesh)  
- **Margins** → boundary volumes with warning shaders  
- **Tensors** → shader params, particle systems, camera effects  
- **AudioField** → AudioSource + mixer routing  
- **HapticField** → XR Interaction Toolkit haptics

**Loop:**

- Poll NDH state → update scene → apply accessibility (e.g., audio‑only, low‑contrast) → log JDTR events.

---

## 3. Unreal integration pattern

**Mapping:**

- **GeometryEnvelope** → Actors, Components, Levels  
- **Basins** → trigger volumes  
- **Corridors** → splines / navigation paths  
- **Margins** → post‑process volumes, warning materials  
- **Tensors** → material parameters, Niagara systems  
- **AudioField** → MetaSounds / Wwise / FMOD  
- **HapticField** → controller feedback via platform APIs

**Loop:**

- NDH state → Blueprint/C++ mapping → apply accessibility (quiet mode, simplified geometry) → HRD‑checked intensity → JDTR logging.

---

## 4. Godot / Web / Mobile integration pattern

**Godot:**

- Geometry → Nodes/Areas  
- Basins → Areas with signals  
- Corridors → Paths  
- Margins → visual overlays  
- AudioField → AudioStreamPlayer  
- HapticField → platform haptics (mobile)

**Web / WebXR:**

- Geometry → Three.js / WebGL scene  
- Basins/Corridors/Margins → meshes + interaction zones  
- AudioField → Web Audio API  
- HapticField → Gamepad haptics / WebXR haptics

**Mobile:**

- Use simplified geometry + strong audio/haptic mapping per accessibility profile.

---

## 5. XR (OpenXR / Vive / Index / PSVR2)

**Mapping:**

- GeometryEnvelope → XR space  
- Basins → safe zones  
- Corridors → guided paths  
- Margins → visual + audio + haptic warnings  
- AudioField → spatial audio sources  
- HapticField → controller vibration patterns

**Rules:**

- Respect NDH **sensory safety constraints** (max amplitude, max flash rate, etc.).  
- Apply **cognitiveEase** (slow transitions, gentle haptics) when requested.

---

## 6. Accessibility integration pattern

Across all clients:

- Read `accessibilityProfile`, `sensoryMode`, `cognitiveEase`, `fallbackPriority`.  
- Ensure:
  - visual cues → audio/haptic/text equivalents  
  - audio cues → visual/text equivalents (unless profile forbids)  
  - intensity reduced in Soft/Quiet/Gentle modes  
  - transitions slowed in cognitive‑ease mode  
- Fail any rendering plan that violates HRD accessibility validation.

---

