## Requirements

* Client:
  * use wasm (yew)
* Backend:
  * rust
  * read audio file from spotifyc
  * extract frequency spectrum/EQ chart
  * take a list of modifications
  * read new audio
  * extract drum info
  * send array of [kick, tom, snare, overhead, hithat] in REALTIME
  * GPIO LED
    * https://github.com/golemparts/rppal#gpio

## EQ

From [here](https://jamaddict.com/the-ultimate-drums-eq-chart/)


```json
[
  // put array[0] through HPF
  {
    fhz: 50,
    db: -2,
  },
  ...
  // put array[n] through LPF
  {
    fhz: 2000,
    db: -1,
  }
]

```

**KICK**
* (-1) — <50hz
* (+1) — 80-200hz
* (-1) — 200-300hz
* (+1) — 500-1500hz
* (-1) — 2000hz>

**SNARE**
* (-1) — 150hz
* (+1) —150-250hz
* (-1) —500-800hz
* (+1) — 1500-4500hz

**TOMS**
* (-1) — 30-50hz
* (+1) — 60-120hz
* (-1) 300-800hz
* (+1) — 2000hz-4000hz

**OVERHEADS**
* (-1) — up to 50-100hz
* (-1) — 300-500hz
* (+1) — 5000hz

**HIHAT**
* (-1) — 150-200hz
* (+1) — 200-300hz
* (-1) — 1000hz
* (+1) — 3000hz

**ROOM MIC**
* (-1) — 80hz
* (+1) — 100hz
* (-1) — 200-300hz
* (-1) — 600-800hz
* (-1) — 2000hz
