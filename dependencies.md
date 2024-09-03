# Proje Bağımlılıkları

Projede kullanılan temel paketler ve işlevleri aşağıda listelenmiştir:

## State Management
- **flutter_redux**: ^0.10.0
- **redux**: ^5.0.0
- **redux_epics**: ^0.15.1

Bu paketler, uygulama state'inin yönetimi için kullanılmaktadır. Redux, merkezi state yönetimi sağlarken, flutter_redux Flutter entegrasyonunu, redux_epics ise yan etkilerin yönetimini kolaylaştırmaktadır.

## Network İşlemleri
- **http**: ^1.2.2

HTTP istekleri için kullanılmaktadır.

## Localization
- **intl**: ^0.19.0

Uygulama içi çoklu dil desteği için kullanılmaktadır.

## Security
- **flutter_secure_storage**: ^9.2.2

Hassas verilerin (örneğin, token'ların) güvenli bir şekilde depolanması için kullanılmaktadır.

## Application Context
- **one_context**: ^4.0.0

Uygulama genelinde tek bir context kullanımını sağlamak için eklenmiştir.

## UI Components
- **icons_plus**: ^5.0.0
- **lottie**: ^3.1.2

icons_plus ek icon setleri, lottie ise animasyonlar için kullanılmaktadır.

## Özel Geliştirilen Paketler
- **authwebview**: ^1.0.4

OAuth akışlarını yönetmek için özel olarak geliştirilmiş bir pakettir. WebView'i uygulama içinde kullanarak authentication işlemlerini gerçekleştirmektedir.

- **jsonata_flutter**: ^0.0.2

JSONata'yı Flutter ortamında kullanabilmek için geliştirilmiş özel bir pakettir. Flutter ve JavaScript arasında köprü kurarak, JSONata sorgularının Flutter içinde çalıştırılmasını sağlamaktadır. Kompleks JSON işlemleri için kullanılmaktadır.

## Diğer
- **flutter_native_splash**: ^2.4.1

Uygulama açılış ekranının özelleştirilmesi için kullanılmaktadır.

