![image](https://github.com/Caycon/RSA/assets/97203151/064b25b8-c6df-4f93-89e1-4ebc1f7bd08e)
- Code python sử dụng phương pháp phân tích Fermat:
```Python
import math

def isqrt(n):
    # Hàm tính căn bậc hai với tối ưu hóa
    x = n
    y = (x + n // x) // 2
    while y < x:
        x = y
        y = (x + n // x) // 2
    return x

def fermat(n):
    # Trường hợp đặc biệt khi n là số chẵn
    if n % 2 == 0:
        return 2, n // 2

    a = isqrt(n)
    b2 = a*a - n
    b = isqrt(b2)
    max_iterations = 10000
    count = 0
    while b*b != b2:
        a += 1
        b2 = a*a - n
        b = isqrt(b2)
        count += 1
        if count > max_iterations:
            raise Exception("Không thể phân tích sau {} lần lặp".format(max_iterations))

    p = a + b
    q = a - b
    assert n == p * q
    return p, q
def main():
    n = 163325259729739139586456854939342071588766536976661696628405612100543978684304953042431845499808366612030757037530278155957389217094639917994417350499882225626580260012564702898468467277918937337494297292631474713546289580689715170963879872522418640251986734692138838546500522994170062961577034037699354013013
    p, q = fermat(n)
    print("p =", p)
    print("q =", q)
if __name__ == '__main__':
    main()
```
![image](https://github.com/Caycon/RSA/assets/97203151/0bdb915b-c1f7-4ea7-a531-61d0cd25d241)
![image](https://github.com/Caycon/RSA/assets/97203151/0e80b0bb-d5f8-4174-b04b-32e5752d684d)



