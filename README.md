AI ánh xạ bàn phím T9 (Bàn phím điện thoại cổ xưa) nó sẽ suggest từ chính xác cho đỡ phải nhấn phím lâu
<img width="640" height="787" alt="image" src="https://github.com/user-attachments/assets/138f03fb-0421-4f0c-8bc8-c18b79711dcd" />

Usage
python main.py 843              # the tie
python main.py 4663             # gone good home
python main.py 843 4663 2255    # batch lookup
python main.py                  # prints all 617 words
from main import unfold, t9
words = unfold()                # ['able', 'about', ..., 'young']
ix = t9()                       # {'843': ['the', 'tie'], ...}
How It Works
The 1,048-character blob is 838 bytes of bz2-compressed data encoded in base85. Inside the blob: 617 English words, reversed and delta-encoded. Each entry is a single digit (shared prefix length with the previous word) followed by the novel suffix, space-separated.

Why reversed? English words share more suffixes than prefixes:

  -ing:  ring, king, sing, bring, thing, ...
  -er:   under, over, after, never, ...
  -ed:   used, need, based, ...
Reversing converts suffix overlap into prefix overlap. Delta encoding captures it. bz2's Burrows-Wheeler Transform compresses the result 30 bytes smaller than the forward-sorted version. The [::-1] in the decoder costs 5 bytes. Net: -25 bytes.

The T9 keypad mapping is computed, not stored:

digit = (ord(c) - 91 - (c>'r') - (c>'y')) // 3
This formula handles the irregular 4-letter groups (PQRS=7, WXYZ=9) with boolean arithmetic. No lookup table needed.
