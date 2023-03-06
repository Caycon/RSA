# Encode RSA basic
```Python



print('Chuỗi cần mã hóa: ', end= '')
a= str(input())
p= int()
q= int()
d= str()
print('Chọn p, q là 2 số nguyên tố: ')
print('p= ', end= '')
p= int(input())
print('q= ',end= '')
q= int(input())
n= int()
n= p*q
print('n= ', n)
phi= (p-1)*(q-1)
print('Chọn e( e là số nguyên tố đôi 1 với phi):')
e= int()
print('e= ',end= '')
e= int(input())
for i in range (0, len(a)):
    m= a[i].encode().hex()
    m= int(m.encode().hex())
    c= str(pow(m, e, n))
    d= d+' '+ c
print('c=', d)


```
Lưu ý các điều kiện:  
Với chuỗi ký tự cần mã hóa ta cần mã hóa mỗi ký tự thành 1 số thì mới mới có thể mã hóa qua RSA.  
Chọn p, q phải là 2 số nguyên tố, để cho bảo mật tốt hơn thì nên lấy q, p là số nguyên tố lớn.  
Chọn e là số nguyên tố đôi 1 với phi (nên chọn số lớn).  
Ta mã hóa qua công thức sau c= (m mũ e) mod(N).  
Để ng nhận có thể giải mã đc thì ta cần tiết lộ khóa công khai là: c, n, e.  
Hoặc khóa bảo mật là: c, n, d.  
Với d thỏa mãn: m= (c mũ d) mod(n).  
Hay d= pow(e, -1, phi).  


