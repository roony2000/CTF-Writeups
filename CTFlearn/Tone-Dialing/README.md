# 🔊 CTFlearn – Tone Dialing

## ☘️ Challenge Information
- **Category:** Cryptography  
- **Difficulty:** Easy  
- **Platform:** CTFlearn  

---

## 📝 Description

The challenge gives a short story and an audio file:

- Audio file: `you_know_what_to_do.wav`

The text mentions:
- A phone call  
- Thinking about the **24 hour clock**

This hints that the solution has something to do with **phone tones / dialing**, i.e. **DTMF tones**.

---

## 🛠 Steps to Solve

### 1️⃣ Decode the phone tones (DTMF)

1. Download the file `you_know_what_to_do.wav`.
2. Open any **online DTMF decoder** (phone tone decoder).
3. Upload the `.wav` file and run the decoder.

The tool prints a sequence of digits.  
In my case, the decoded result at the bottom was:

```text
67847010810197110123678289880847918265807289125

This looks like one long decimal number, but the range of the values suggests ASCII codes.

🔢 2️⃣ Extracting the Numbers from the Audio (DTMF)

Instead of automatically splitting the digits, I listened to the audio manually.
The WAV file contains DTMF tones — the distinct sounds produced when pressing phone keypad numbers.

By carefully listening:

I identified each button press based on its tone

Noted the pauses between tones to determine where each digit ends

Wrote down all digits in the correct order as they appeared in the audio

This produced the full numeric sequence needed for the next step of decoding.

3️⃣ Convert decimal to text (CyberChef)

1.Open CyberChef.

2.Add the operation “From Decimal”.

3.Use Space as the delimiter.

4.Paste the decimal values:

67 84 70 108 101 97 110 123 67 82 89 80 84 79 71 82 65 80 72 89 125

5.Run the recipe.

The output is:
CTFlearn{CRYPTOGRAPHY}


🎯 Takeaways

Phone beeps in challenges usually mean DTMF (tone dialing).

Long digit sequences often hide ASCII codes (decimal, hex, or octal).

CyberChef is perfect for quick decimal → text conversion.ا
