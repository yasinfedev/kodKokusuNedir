# Kod kokusu nedir?
**Kod kokusu (Code Smell)**, bir yazılım kodunda sorunlu bir tasarım veya geliştirme pratiğini işaret eden ve kodun:

+ Bakımı zorlaştıran,
+ Anlaşılabilirliğini azaltan,
+ Hatalara açık hale getiren
belirtilerdir. Kod kokusu, doğrudan bir hataya neden olmaz; ancak uzun vadede kod kalitesini düşürerek problemlere yol açabilir.

Terim, ilk olarak **Martin Fowler** ve **Kent Beck** tarafından tanımlanmıştır ve genellikle kodun **refactor edilmesi** (yeniden düzenlenmesi) gerektiğine işaret eder.

---

# Kod Kokusu Örnekleri ve Çözümleri
## 1. Çok Uzun Fonksiyonlar (Long Method)
Bir fonksiyonun çok uzun olması, onun anlaşılmasını ve test edilmesini zorlaştırır.
**Örnek:**

```
func processOrder() {  
    // 100'den fazla satırlık işlem kodları  
}
```

**Çözüm:** Fonksiyonu daha küçük, anlamlı parçalara ayırmak.

## 2. Tekrarlayan Kod (Duplicated Code)
Aynı veya benzer kod parçalarının birden fazla yerde bulunması.
**Örnek:**

```
let discount = price * 0.10
let totalWithDiscount = price - discount

// Başka bir yerde aynı işlem tekrarlanır
let discount2 = anotherPrice * 0.10
let totalWithDiscount2 = anotherPrice - discount2
```

**Çözüm:** Ortak kod parçalarını bir fonksiyona veya yardımcı bir yapıya taşımak.

## 3. Tanımsız Sınıf Amacı (God Object / God Class)
Bir sınıfın çok fazla sorumluluğa sahip olması ve neredeyse tüm işlemleri gerçekleştirmesi.
**Çözüm:** Tek Sorumluluk İlkesi'ne (Single Responsibility Principle) uygun bir tasarıma geçmek.

## 4. Aşırı Uzun Parametre Listesi (Long Parameter List)
Bir fonksiyon veya metodun çok fazla parametre alması, okunabilirliği ve kullanım kolaylığını azaltır.
**Örnek:**

```
func createUser(name: String, surname: String, age: Int, address: String, phone: String) {
    // İşlem
}
```

**Çözüm:** Parametreleri bir model veya yapı (struct) içine almak.

## 5. İsimlendirme Sorunları (Poor Naming Conventions)
Değişkenlerin, fonksiyonların veya sınıfların isimlerinin yaptıkları işlemi ifade etmemesi.
**Örnek:**

```
let x = 5 // "x" neyi temsil ediyor?
func doSomething() { } // "doSomething" ne yapıyor?
```

**Çözüm:** Anlamlı ve standartlara uygun isimlendirme yapmak.

## 6. Yersiz Bağımlılıklar (Inappropriate Coupling)
Modüllerin veya sınıfların birbirine aşırı bağımlı olması.
**Çözüm:** Bağımlılıkları azaltmak için arayüzler veya soyutlamalar kullanmak.

## 7. Kullanılmayan Kod (Dead Code)
Artık kullanılmayan, ancak kod tabanında hala mevcut olan kod parçaları.
**Çözüm:** Kullanılmayan kodları tespit edip temizlemek.

## 8. Aşırı Karmaşıklık (Overcomplicated Code)
Bir çözümün gereksiz yere karmaşık hale getirilmesi.
**Çözüm:** Daha basit ve anlaşılır bir çözüm uygulamak.

---

# Kod Kokusunu Tespit Etme ve Çözme
## 1.Kod Gözden Geçirme (Code Review):
Ekip arkadaşlarının kodu incelemesi, kod kokusunu erken fark etmenizi sağlar.

## 2.Otomatik Araçlar:
Kod analizi araçları, kod kokusunu tespit etmede yardımcı olabilir.
**Örnek Araçlar:** SonarQube, ESLint, SwiftLint.

## 3.Refactoring (Yeniden Düzenleme):
Kodun yapısını iyileştirerek daha temiz, okunabilir ve sürdürülebilir hale getirmek.

---

# Kod Kokusunu Önlemek İçin İpuçları
## 1.Temiz Kod İlkelerine Uyun:
+ Martin Fowler’ın refactoring prensipleri ve Robert C. Martin’in temiz kod ilkeleri rehber olabilir.
## 2.Küçük ve Anlamlı Fonksiyonlar Yazın:
+ Her fonksiyon tek bir işi yapmalıdır.
## 3.Sorumlulukları Dağıtın:
+ Sınıflar ve modüller tek bir sorumluluğa sahip olmalıdır.
## 4.Kod Standartlarını Takip Edin:
+ Ekibinizle bir kod standartları rehberi belirleyin ve buna uyun.

---

**Kod kokusu**, kötü bir kodlama pratiğinin işareti olabilir; ancak erken tespit edilip düzeltildiğinde yazılımınızın bakımını ve kalitesini artırabilirsiniz.

