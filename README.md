# Help Bobo Learn — The Three Little Pigs

A working POC of a toddler language app (ages ~3).

A child picks an animal, names it, and then **teaches it words** while a classic
story is read aloud. Each word learned becomes a card in the animal's word book.

## Design rules
- **Nothing ever blocks.** Every prompt waits ~6s then moves on by itself. There is no
  failure state, no retry loop, no "let's try that again".
- **One word maximum.** The child only ever repeats a single word, never a sentence.
- **The child is the teacher.** Bobo is the one who doesn't know the words.
- **Voice is optional.** Detection is loudness-only (no speech recognition, so it works
  in any accent) — and tapping the picture always works instead.

## Tech
Single self-contained `index.html`. Web Speech API for narration, Web Audio for
loudness detection, localStorage for the word book. No accounts, no backend, no tracking.

Microphone requires HTTPS. Over plain http:// the tap path still works.
