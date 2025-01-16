# Variables and Data Types

Değişkenler, verileri sakladığımız kutular olarak düşünülebilir. Veriler bu kutuların içine konur ve her kutunun bir veri tipi vardır. Veri tipleri şunlardır:

- **byte**
- **short**
- **int**
- **long**
- **float**
- **double**
- **boolean**
- **char**
- **string**

## Tam Sayılar İçin Kullanılan Veri Tipleri

### byte
- Tam sayıları saklamak için kullanılır.
- 1 byte yer kaplar.
- -128 ile 127 arasındaki değerleri kapsar.

### short
- Tam sayı saklar.
- byte veri tipinden daha geniş bir aralığı vardır.
- 2 byte yer kaplar.

### int
- Tam sayılar için en sık kullanılan veri tipidir.
- 4 byte yer kaplar.
- 9-10 basamaklı sayılara kadar çıkabilir.
- Örneğin: Kullanıcının TC Kimlik numarasını saklamak için yetersizdir çünkü int en fazla 10 basamaklı sayıları destekler.

### long
- Daha büyük tam sayıları saklamak için kullanılır.
- 8 byte yer kaplar.
- TC Kimlik numarası gibi 11 basamaklı sayıları saklamak için uygundur.

## Ondalıklı Sayılar İçin Kullanılan Veri Tipleri

### float
- Ondalıklı sayıları saklar.
- 2 byte yer kaplar.
- Sınırlı bir hassasiyete sahiptir.

### double
- Ondalıklı sayıları saklar.
- 4 byte yer kaplar.
- float veri tipine göre daha hassastır.

## Diğer Veri Tipleri

### boolean
- true veya false değerlerini saklar.

### char
- Tek bir karakteri saklar.

### string
- Metin verilerini saklar.

## Değişken Nasıl Tanımlanır?

Bir değişken tanımlarken aşağıdaki adımları izleriz:

1. Değişkenin veri tipi belirlenir.
2. Değişken adı ve değeri tanımlanır.

**Örnek:**
```csharp
int a = 5;
string metin = "Merhaba";
```
- Metin değerleri çift tırnak (") içerisinde tanımlanır.

## Değişken Tanımlarken Dikkat Edilmesi Gerekenler

1. Değişken adı rakamla başlayamaz.
   ```csharp
   int 1a = 5; // Hatalı
   ```

2. Değişken adı boşluk içeremez.
   ```csharp
   int a b = 5; // Hatalı
   ```

3. Türkçe karakter kullanılmamalıdır.
   ```csharp
   int çelik = 5; // Hatalı
   ```

