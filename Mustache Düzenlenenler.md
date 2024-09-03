# Mustache Değişiklikleri

## 1. Parametre Ekleme Düzeltmesi

**Dosya:** `api_helper.mustache`

**Sorun:** Requeste eklenen parametreler yanlış ekleniyordu. Bu durum `filter`, `include` veya `where` kullanmamızı engelliyordu.

**Çözüm:** Aşağıdaki görüntüde gösterilen kod değişikliği ile bu sorun giderildi:

![Parametre Ekleme Düzeltmesi](images/image%20(1).png)

Bu değişiklik, parametrelerin doğru bir şekilde JSON formatına dönüştürülmesini sağlayarak, `filter`, `include` ve `where` gibi işlemlerin düzgün çalışmasına olanak tanıdı.

## 2. Map ve Object için listFromJson Metodu Eklenmesi

**Sorun:** Map ve Object için `listFromJson` metodu varsayılan olarak bulunmuyordu. Bu durum, bu tipleri kullanan metodların çalışmamasına neden oluyordu.

**Çözüm:** Aşağıdaki görüntüde gösterilen extension'lar eklenerek bu sorun giderildi:

![Map ve Object Extension'ları](images/image%20(2).png)

Bu extension'lar sayesinde, Map ve Object tipleri için `listFromJson` metodu kullanılabilir hale geldi, böylece bu tipleri kullanan metodlar artık hatasız çalışabiliyor.

## 3. Any Tipi için TypeDef Tanımlanması

**Dosya:** `apilib.mustache`

**Değişiklik:** Any tipi için TypeDef yapıldı.

![Any TypeDef](images/image%20(3).png)

Bu değişiklik, `Any` tipinin `dynamic` olarak tanımlanmasını sağladı. Bu, kodun daha esnek ve genel amaçlı kullanımını mümkün kılıyor.

## 4. Constructor Syntax Hatası Düzeltmesi

**Dosya:** `dart_constructor.mustache`

**Sorun:** Constructor yapısındaki syntax hatasına neden olan süslü parantez sorunu vardı.

**Çözüm:** Aşağıdaki görüntüde gösterilen değişiklik ile bu sorun giderildi:

![Constructor Syntax Düzeltmesi](images/image%20(4).png)

Bu değişiklik, constructor'daki süslü parantezlerin doğru kullanımını sağlayarak syntax hatasını ortadan kaldırdı. Bu sayede Dart sınıflarının doğru bir şekilde oluşturulması sağlandı.

## 5. Native Class Syntax Hatalarının Düzeltilmesi

**Dosya:** `native_class.mustache`

**Sorun:** İlgili native sınıflar oluşturulurken, standart metotların oluşturduğu syntax hataları vardı.

**Çözüm:** Aşağıdaki görüntüde gösterilen değişiklikler ile bu sorunlar giderildi:

![Native Class Syntax Düzeltmesi](images/image%20(5).png)

Bu değişiklikler, native sınıfların doğru bir şekilde oluşturulmasını sağlayarak syntax hatalarını ortadan kaldırdı.

## 6. Null Parametre Gönderimi Sorununun Çözülmesi

**Dosya:** `native_class.mustache`

**Sorun:** Requeste eklenen null parametrelerin gönderilmesi bir sorun oluşturuyordu.

**Çözüm:** Aşağıdaki görüntüde gösterilen değişiklik ile null olan parametreler artık gönderilmiyor:

![Null Parametre Çözümü](images/image%20(6).png)

Bu değişiklik, null değerlerin gereksiz yere gönderilmesini engelleyerek daha temiz ve etkili bir request yapısı sağladı.

## 7. Complex Type'lar için listFromJson Metodu Eklenmesi

**Dosya:** `native_class.mustache`

**Sorun:** Bazı complex type'ların listFromJson metodunun oluşmaması ya da hatalı oluşması sorun yaratıyordu.

**Çözüm:** Extension kullanımı çözümüne gidildi ve template aşağıdaki gibi düzenlendi:

![Complex Type listFromJson Çözümü](images/image%20(7).png)

Bu değişiklik, complex type'lar için listFromJson metodunun doğru bir şekilde oluşturulmasını sağladı.

## 8. listFromJson Extension'ının Tanımlanması

**Dosya:** `native_class.mustache`

**Değişiklik:** listFromJson extension'ı sayfanın en alt kısmında tanımlandı.

![listFromJson Extension Tanımı](images/image%20(8).png)

Bu ekleme, listFromJson metodunun tüm gerekli sınıflar için kullanılabilir olmasını sağladı.


## 9.Örnek Cli
```bash
openapi-generator-cli generate -i openapiconfig/open.json -g dart -o lib/services/sdk -t lib/dart2 --skip-validate-spec
```

