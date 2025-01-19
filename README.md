# Değişkenler ve Veri Tipleri

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

# Koşul Yapıları ve Döngüler

## Koşul Yapıları (if - else)

Koşul yapıları, bir şartın sağlanıp sağlanmadığını kontrol etmek için kullanılır.

**Yapısı:**
```csharp
if (şart)
{
    // Şart doğruysa çalışacak kodlar
}
else
{
    // Şart yanlışsa çalışacak kodlar
}
```

Eğer if koşulu `true` değerine sahipse if bloğu çalışır. Eğer koşul sağlanmazsa else bloğu devreye girer. Temel yapı bu şekildedir.

### Örnek:
Öğrencinin notu 50'den büyükse "Başarılı", aksi takdirde "Başarısız" yazdıralım:

```csharp
int not = 75;
if (not > 50)
{
    Console.WriteLine("Başarılı");
}
else
{
    Console.WriteLine("Başarısız");
}
Console.ReadLine();
```

Bu örnekte `not` değişkeninin değeri 75 olduğu için if bloğu çalışacak ve "Başarılı" yazdırılacaktır. else bloğu çalışmayacaktır.

## else if Yapısı

Birden fazla durumun kontrol edilmesi gerektiğinde `else if` yapısı kullanılır.

**Yapısı:**
```csharp
if (şart1)
{
    // Şart1 doğruysa çalışacak kodlar
}
else if (şart2)
{
    // Şart2 doğruysa çalışacak kodlar
}
else
{
    // Hiçbir şart sağlanmazsa çalışacak kodlar
}
```

### Örnek:
Kullanıcıdan üç not alıp ortalamasını hesaplayalım. Not aralıklarına göre harf notunu yazdıralım:

```csharp
Console.WriteLine("Lütfen birinci notunuzu giriniz:");
int birinci_not = Convert.ToInt32(Console.ReadLine());
int ikinci_not = Convert.ToInt32(Console.ReadLine());
int ucuncu_not = Convert.ToInt32(Console.ReadLine());

// Burada ReadLine ile notu string olarak alıyoruz. Ancak not üzerinde matematiksel işlemler yapılacağı için Convert ile int'e çeviriyoruz.

int sonuc = (birinci_not + ikinci_not + ucuncu_not) / 3;
if (sonuc >= 80 && sonuc <= 100)
{
    Console.WriteLine("A+");
}
else if (sonuc >= 60 && sonuc < 80)
{
    Console.WriteLine("A");
}
else if (sonuc >= 40 && sonuc < 60)
{
    Console.WriteLine("B+");
}
else
{
    Console.WriteLine("F");
}
```

## switch-case Yapısı

`switch` yapısı, bir değişkenin belirli bir değer alıp almadığını kontrol etmek için kullanılır.

**Yapısı:**
```csharp
switch (deger)
{
    case deger1:
        // Kodlar
        break;
    case deger2:
        // Kodlar
        break;
    default:
        // Hiçbir case sağlanmazsa çalışacak kodlar
        break;
}
```

### Açıklama:
- `switch` içindeki değer hangi `case` ile eşleşirse o bloğa girer.
- Bir sonraki `case` bloğuna geçilmemesi için `break` ifadesi kullanılır.

### Örnek:
```csharp
int gun = 3;
switch (gun)
{
    case 1:
        Console.WriteLine("Pazartesi");
        break;
    case 2:
        Console.WriteLine("Salı");
        break;
    case 3:
        Console.WriteLine("Çarşamba");
        break;
    default:
        Console.WriteLine("Geçersiz gün");
        break;
}
```

# Döngüler (Loops)

## for Döngüsü

`for` döngüsü, belirli bir koşul sağlanana kadar belirli işlemleri tekrar etmek için kullanılır. Aşağıdaki örnekte 1'den 10'a kadar olan sayılar alt alta yazdırılacaktır.

**Örnek:**
```csharp
for (int i = 1; i <= 10; i++)
{
    Console.WriteLine(i);
}
Console.ReadLine();
```

## while Döngüsü

`while` döngüsü, belirtilen şart doğru olduğu sürece kod bloklarını tekrarlar. `for` döngüsünün alternatifidir.

**Örnek:**
```csharp
int i = 1;
while (i <= 10) // i 10'a kadar artacak
{
    Console.WriteLine(i); // i'yi alt alta yazdır
    i++; // i'nin değerini 1 artır
}
```

## foreach Döngüsü

`foreach` döngüsü, diziler (veya koleksiyonlar) üzerinde tek tek gezilerek işlem yapmak için kullanılır. 

**Örnek:**
```csharp
string[] isimler = { "Sitran", "Şeri", "Sena" };

foreach (string a in isimler)
{
    Console.WriteLine(a);
}
```

Burada önce bir dizi (koleksiyon) belirledik, bu örnekte `isimler` adlı bir dizi kullanılmıştır.
