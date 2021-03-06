Döngü kullanarak çözümü:

```js run
function topla(n) {
  let toplam = 0;
  for (let i = 1; i <= n; i++) {
    toplam += i;
  }
  return toplam;
}

alert( topla(100) );
```

Özçağrı kullanarak toplama:

```js run
function topla(n) {
  if (n == 1) return 1;
  return n + topla(n - 1);
}

alert( topla(100) );
```

Aritmetik işlemler ile toplama: `topla(n) = n*(n+1)/2`:

```js run
function topla(n) {
  return n * (n + 1) / 2;
}

alert( topla(100) );
```

Not: Doğal olarak formül en hızlı olanırıd. `n`'in her değeri için 3 defa operasyon yapmaktadır. Matematik yardımcı olur!

Döngü hız bakımından ikinci sırada yer alır. Döngüde ve özçağrıda aynı sayılar toplanır. Fakat özçağrı iç içe çağrılar kullanarak çalışıtırma yığını yönetimi gerektirir. Bu da ayrıca bir kaynak demektir, bundan dolayı yavaştır.

Not2: Eğer özçağrının son fonksiyonunda ise ( `topla` gibi ) dıştaki fonksiyon çalışmayı devam ettirmez ve çalıştırma kaynağının bilinmesine gerek yoktur. Bundan dolayı `topla(100000)` hesaplanabilirdir. Fakat JavaScript motoru bunu desteklemiyor ise bu durumda maksimum yığın geçildi hatası verecektir. Bunun nedeni yığının belirli bir sınırının olmasıdır. 