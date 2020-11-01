# ReleaseName

Change Apk name after build Apk

- `build.gradle(:app)`

```gradle
android {
    def appName = "AppName"
    def date = new Date()
    def formattedDate = date.format('yyyyMMdd.HHmmss')

    buildTypes {
        debug {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'

            applicationVariants.all { variant ->
                variant.outputs.all {
                    def flavor = variant.name
                    def versionName = variant.versionName
                    outputFileName = "${appName}_${versionName}.${formattedDate}_${flavor}.apk"
                }
            }
        }
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android-optimize.txt'), 'proguard-rules.pro'

            applicationVariants.all { variant ->
                variant.outputs.all {
                    def flavor = variant.name
                    def versionName = variant.versionName
                    outputFileName = "${appName}_${versionName}.${formattedDate}_${flavor}.apk"
                }
            }
        }
    }
}
```

---

```
Copyright 2020 M. Fadli Zein
```
