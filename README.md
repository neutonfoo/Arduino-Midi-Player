# Arduino .midi Player

Due to Arduino only having 2 usable hardware timers, only .midi files that have 2 tracks will play properly.

\* 1 Piano Part = 2 Tracks

**Requires ToneLibrary** - Can be installed through Tools &rarr; Manage Libraries

1. Get .midi file (for example on https://musescore.org/)

2. Rename .midi file to song.midi and place in folder containing index.html

3. Launch index.html

4. Arduino commands will be generated

5. Copy and paste into the `loop()` function of buzmus.ino

   * May need to trim song if it exceeds Arduino storage limits
     * In my experience, I can usually cut it to ~1600 lines of code

   * Some songs may not sound correct since only 1 note can only be played on each buzzer
     * Chords / Multiple notes at the same time on the same track will sound bad

## Buzmus.ino

"*buzzer music*"

The Arduino Sketch file

```c
#include <Tone.h>

// Due to hardware limitations, will only support 2 tracks max

Tone freq0;
Tone freq1;

void setup() {
  Serial.begin(9600);
  freq0.begin(10); // Change pins if needed
  freq1.begin(11);
}

void loop() {
	// Paste generated code here. 
  // End with while(1); to only play once
}
```

