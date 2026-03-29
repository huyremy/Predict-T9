# AI ánh xạ bàn phím T9

**Bàn phím điện thoại cổ xưa** — AI sẽ suggest từ chính xác giúp bạn đỡ phải nhấn phím nhiều lần.

![T9 Keyboard Demo](https://github.com/user-attachments/assets/138f03fb-0421-4f0c-8bc8-c18b79711dcd)

## Usage (Cách sử dụng)

### Command Line

```bash
python main.py 843              # → the tie
python main.py 4663             # → gone good home
python main.py 843 4663 2255    # batch lookup
python main.py                  # in ra tất cả 617 từ
```
# Dùng trong Python code:
```Python
from main import unfold, t9

words = unfold()          # ['able', 'about', ..., 'young']

ix = t9()                 # {'843': ['the', 'tie'], ...}
