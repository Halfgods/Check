This experiment teaches you how to recover both plaintext and the secret shift key in a Shift Cipher (Caesar Cipher) using cryptanalysis. Follow this single workflow from PART I to PART IV.

### STEP 1: Understand the Challenge (PART I)

In PART I - Decryption Challenge:

- Read the ciphertext shown in the challenge box.
- Your objective is to recover both:
  - the plaintext
  - the shift key
- Use Next Ciphertext to cycle through different challenges.
- Each challenge has a different plaintext-key pair.

Example challenge:

- Ciphertext: `haahjr ha khdu`
- Expected recovery: `attack at dawn` with shift 7

### STEP 2: Analyze in the Workspace (PART II)

Use PART II - Analysis Workspace to infer possible keys before final submission.

#### A) Frequency Analysis

Click Frequency Analysis to generate:

- Letter distribution table
- Observation fields:
  - Most frequent ciphertext letter
  - Estimated corresponding plaintext letter
  - Possible shift value
  - Remarks

How to use it:

- Compare dominant ciphertext letters with common English frequencies.
- Treat the suggested shift as a hypothesis, not guaranteed truth.
- Validate the hypothesis using Test All Shifts or PART III.

#### B) Test All Shifts

Click Test All Shifts to perform brute-force decryption for all 26 keys.

- The full list of keys 0-25 is displayed.
- A most probable candidate is automatically highlighted.
- A summary is included:
  - Total Keys Tested
  - Most Probable Key
  - Reason

How to use it:

- Scan all rows, not only the highlighted one.
- Look for meaningful English words and coherent sentence structure.
- Cross-check the likely key in PART III.

#### C) Rough Work and Clear

- Use the workspace text area to record assumptions, key trials, and interim findings.
- Use Clear to reset only rough work content when needed.

### STEP 3: Verify in Simulator (PART III)

Use PART III - Shift Cipher Simulator to test hypotheses.

For encryption check:

- Enter candidate plaintext.
- Select candidate key.
- Click Encrypt and compare against PART I ciphertext.

For decryption check:

- Enter ciphertext in the simulator ciphertext box.
- Select candidate key.
- Click Decrypt and inspect readability.

Purpose:

- Confirm whether your inferred key produces consistent encryption/decryption behavior.

### STEP 4: Submit Solution (PART IV)

When you are confident:

- Enter the recovered plaintext.
- Select the recovered key.
- Click Check my answer.

Feedback behavior:

- If correct, the simulation reports:
  - Recovered Key
  - Recovered Plaintext
  - Method Used
  - Keys Tested
  - Conclusion
- If incorrect, the simulation provides guidance (without revealing the final answer), including prompts to:
  - review frequency analysis
  - compare Test All Shifts outputs
  - verify selected key using PART III

### STEP 5: Learn from Verification

After a correct submission:

- PART III is auto-populated to demonstrate verification.
- You can observe that the recovered plaintext and key regenerate the challenge ciphertext.
- Use Next Ciphertext to repeat the same methodology on a new challenge.

### Example Walkthrough

Given ciphertext: `KRZ DUH BRX`

1. Run Test All Shifts.
2. Observe candidate outputs:
   - k=0: krz duh brx
   - k=1: jqy ctg aqw
   - k=2: ipx bsf zpv
   - k=3: how are you (meaningful English)
3. Verify in PART III:
   - plaintext: how are you
   - shift: 3
   - encrypt result should match KRZ DUH BRX
4. Submit in PART IV:
   - plaintext: how are you
   - key: 3

### Tips for Effective Cryptanalysis

- Start with PART II before trying random keys.
- Use frequency analysis for initial hypothesis generation.
- Use Test All Shifts for exhaustive comparison.
- Use PART III to verify key-plaintext consistency.
- Use PART IV feedback to iterate methodically.
