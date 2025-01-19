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

#  Diziler (Arrays)

#### **Diziler Nedir?**
C# dilinde **diziler (arrays)**, aynı türdeki birden fazla veriyi bir arada saklamak için kullanılan veri yapılarıdır. Diziler, sabit boyutludur, yani boyutları tanımlandıktan sonra değiştirilemez.

---

#### **Dizilerle İlgili Temel Bilgiler**
1. **[] Bu işaret dizileri ifade eder.**  
   Diziler her zaman köşeli parantez `[]` kullanılarak tanımlanır.

2. **Veri tipini uygun tanımlamak gerekir.**  
   Dizilerde yalnızca tanımlanan veri tipine uygun elemanlar saklanabilir.

3. **Diziler sıfır indeksle başlar.**  
   Dizilerdeki ilk eleman her zaman `0` indeksine sahiptir.

---

#### **Dizi Tanımlama ve Kullanımı**

1. **Dizi Tanımlama**
   ```csharp
   // Boş bir dizi oluşturma (5 elemanlı)
   int[] sayilar = new int[5];
   ```

2. **Diziye Değer Atama**
   ```csharp
   sayilar[0] = 10; // İlk eleman
   sayilar[1] = 20; // İkinci eleman
   ```

3. **Dizi Tanımlama ve Başlatma**
   ```csharp
   string[] isimler = { "Ali", "Ayşe", "Fatma" };
   ```

4. **Dizi Elemanlarına Erişim**
   ```csharp
   Console.WriteLine(sayilar[0]); // İlk eleman (10)
   Console.WriteLine(isimler[1]); // İkinci eleman ("Ayşe")
   ```

---

#### **Dizi Örneği**

        // Bir dizi tanımlayıp değer atama
        int[] sayilar = { 5, 10, 15, 20, 25 };

        // Tüm elemanları ekrana yazdırma
        for (int i = 0; i < sayilar.Length; i++)
        {
            Console.WriteLine($"Eleman {i}: {sayilar[i]}");
        }

        // foreach ile elemanlara erişim
        Console.WriteLine("Foreach ile:");
        foreach (int sayi in sayilar)
        {
            Console.WriteLine(sayi);
        }
```

**Çıktı:**
```
Eleman 0: 5
Eleman 1: 10
Eleman 2: 15
Eleman 3: 20
Eleman 4: 25
Foreach ile:
5
10
15
20
25
```

---

#### **Dizilerde Önemli Özellikler**

1. **`Length`**: Dizinin eleman sayısını verir.
   ```csharp
   Console.WriteLine(sayilar.Length); // 5
   ```

2. **Çok Boyutlu Diziler**:
   ```csharp
   int[,] matris = new int[2, 3]; // 2 satır, 3 sütun
   matris[0, 0] = 1; // İlk satır, ilk sütun
   matris[1, 2] = 5; // İkinci satır, üçüncü sütun
   ```

---

#### **Özet**
- **Diziler**, birden fazla aynı türdeki veriyi saklamak için kullanılır.
- Diziler, **sıfır indeksiyle** başlar.
- Köşeli parantez `[]` kullanılarak tanımlanır.
- Dizilerin boyutu tanımlandıktan sonra **değiştirilemez**.


---

# Methodlar (Methods)

#### **Methodlar Nedir?**
C# dilinde **methodlar**, yapmak istediğimiz işe hizmet eden kod parçacıklarıdır. Methodlar, kod tekrarını önler ve programlarımızı daha düzenli bir hale getirir.  
Bir method, belirli bir işlevi yerine getiren ve gerektiğinde parametre alabilen veya değer döndürebilen yapılardır.

---

#### **Method Tanımlama**
Methodlar belirli bir yapıdadır ve bu yapı aşağıdaki gibi özetlenebilir:
```csharp
<erişim_belirleyicisi> <geri_dönüş_tipi> <method_adı>(<parametreler>)
{
    // Methodun içindeki işlemler
}
```

**Örnek:**
```csharp
public static void Merhaba()
{
    Console.WriteLine("Merhaba Dünya!");
}
```

---

#### **Method Türleri ve Örnekler**

1. **Parametresiz - Geriye Değer Döndürmeyen Method**
   ```csharp
   static void Main(string[] args)
   {
       // Method çağırma
       Naber();
   }

   static void Naber()
   {
       // Geriye değer döndürmeyen bir method (void)
       Console.WriteLine("Selamlar");
   }
   ```

   **Çıktı:**
   ```
   Selamlar
   ```

---

2. **Parametre Alan - Geriye Değer Döndürmeyen Method**
   ```csharp
   static void Main(string[] args)
   {
       // Methodu doğru şekilde parametrelerle çağırıyoruz
       toplamaYap(5, 7); // 5 ve 7 parametre olarak gönderildi
   }

   static void toplamaYap(int sayi1, int sayi2)
   {
       // Parametrelerle işlem yapıyor
       Console.WriteLine("Gönderilen sayıların toplamı: " + (sayi1 + sayi2));
   }
   ```

   **Çıktı:**
   ```
   Gönderilen sayıların toplamı: 12
   ```

---

3. **Parametre Alan - Geriye Değer Döndüren Method**
   ```csharp
   static void Main(string[] args)
   {
       // Methodu çağır ve dönen sonucu yazdır
       int sonuc = carpmaYap(4, 6);
       Console.WriteLine("Çarpım sonucu: " + sonuc);
   }

   static int carpmaYap(int sayi1, int sayi2)
   {
       // Çarpım işlemini yapıp sonucu döndürür
       return sayi1 * sayi2;
   }
   ```

   **Çıktı:**
   ```
   Çarpım sonucu: 24
   ```

---

#### **Özet**
- **Parametresiz Methodlar**: Herhangi bir bilgi almadan işlem yapar.
- **Parametre Alan Methodlar**: İşlem yapmak için belirli değerleri alır.
- **Geriye Değer Döndüren Methodlar**: İşlemler sonucunda bir değer döndürür.
- **Void Methodlar**: Geriye hiçbir değer döndürmeyen methodlardır.

---


