# pdf_flutter
Latest version: 1.2.0

Inspired by [Pdf_Viewer_Plugin](https://github.com/lubritto/Pdf_Viewer_Plugin) 😇
Wrapped around [AndroidPdfViewer](https://github.com/barteksc/AndroidPdfViewer) on Android. 🙏🏼

### 1. Add `pdf_flutter`on `pubspec.yml` 

    dependencies:
      pdf_flutter:
        git:
          url: git://github.com/LeDuyTho/pdf_flutter
          ref: 1.2.0

### 2. On iOS enable PDF preview like this:

Add this on `ios/Runner/info.plist`:

        <key>io.flutter.embedded_views_preview</key>
        <true/>

### 3. Start Using 

#### Load PDF from network (caches PDF from network)

        PDF.network(
                'https://google-developer-training.github.io/android-developer-fundamentals-course-concepts/en/android-developer-fundamentals-course-concepts-en.pdf',
                height: 500,
                width: 300,
        )
              
#### Load PDF files

        File fileName;  
        PDF.file(
            fileName,
            height: 200,
            width: 100,
        )
        
#### Load PDF from assets

        PDF.assets(
            "assets/pdf/demo.pdf",
            height: 200,
            width: 100,
        )

#### For Production
    Here are the steps to fix:
        1. Add proguard-rules.pro file if its not already there
        
<img src="https://user-images.githubusercontent.com/2768159/91779534-e288fd00-ebc3-11ea-9c6f-d3e3a9d0922c.png">

        2. Inside of the proguard-rules.pro file put this:
            -keep class com.shockwave.**
            -keepclassmembers class com.shockwave.** { *; }
            
        3.In app/build.gradle add this:
<img src="https://user-images.githubusercontent.com/2768159/91779653-37c50e80-ebc4-11ea-8fbb-22d5c8e5a9ed.png">

            shrinkResources true
            minifyEnabled true
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'

## Demo           
![demo](art/pdf_flutter_updated.gif)
