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

