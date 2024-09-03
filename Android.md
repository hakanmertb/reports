
# Android Tarafı Yapılacaklar

## 1. Üst Seviye build.gradle Dosyası Düzenlemeleri

- Mevcut tüm `subprojects` bloklarını silinecek.
- Yerine aşağıdaki yeni kodlar eklenecek:

```gradle
subprojects {
    afterEvaluate { project ->
        if (project.plugins.hasPlugin("com.android.application") ||
                project.plugins.hasPlugin("com.android.library")) {
            project.android {
                compileSdkVersion 34
            }
        }
    }
}

subprojects {
    project.buildDir = "${rootProject.buildDir}/${project.name}"
    project.evaluationDependsOn(':app')
}
```

## 2. Uygulama Seviyesi build.gradle Dosyası Güncellemeleri

### Yeni Bağımlılık Ekleme

- Dosyanın sonuna aşağıdaki bağımlılık eklenecek:

```gradle
dependencies {
    implementation 'com.github.fast-development.android-js-runtimes:fastdev-jsruntimes-jsc:0.3.4'
}
```

### Android Ayarları Güncellemeleri

#### Derleme Türleri

- `buildTypes { release { } }` kısmına aşağıdakiler eklenecek:

```gradle
buildTypes {
    release {
        minifyEnabled true
        proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
    }
}
```

#### Varsayılan Ayarlar

- `defaultConfig {}` kısmına aşağıdakiler eklenecek:

```gradle
defaultConfig {
    minSdkVersion 21
    multiDexEnabled true
}
```

## 3. AndroidManifest.xml Dosyası Düzenlemeleri

- Uygulamanın ihtiyaçlarına göre gerekli izinler eklenecek.
- Örneğin, internet erişimi gerekiyorsa aşağıdaki izin eklenecek:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

---
