# gradle-sync-warning-test-project

Project structure:

* app module with debug and release variants
* library module *with only debug variant*

After syncing it gives a warning:
```
Warning:<i><b>project ':app': Unable to build Kotlin project configuration</b>
Details: org.gradle.api.artifacts.ResolveException: Could not resolve all dependencies for configuration ':app:debugImplementationDependenciesMetadata'.
Caused by: org.gradle.internal.component.AmbiguousVariantSelectionException: More than one variant of project :testlib matches the consumer attributes:
  - Configuration ':testlib:debugApiElements' variant android-aidl:
      - Found artifactType 'android-aidl' but wasn't required.
      - Found com.android.build.api.attributes.BuildTypeAttr 'debug' but wasn't required.
      - Found com.android.build.api.attributes.VariantAttr 'debug' but wasn't required.
      - Found com.android.build.gradle.internal.dependency.AndroidTypeAttr 'Aar' but wasn't required.
      - Required org.gradle.usage 'kotlin-api' and found compatible value 'java-api'.
      - Required org.jetbrains.kotlin.platform.type 'common' but no value provided.
  - Configuration ':testlib:debugApiElements' variant android-classes:
      - Found artifactType 'android-classes' but wasn't required.
      - Found com.android.build.api.attributes.BuildTypeAttr 'debug' but wasn't required.
      - Found com.android.build.api.attributes.VariantAttr 'debug' but wasn't required.
      - Found com.android.build.gradle.internal.dependency.AndroidTypeAttr 'Aar' but wasn't required.
      - Required org.gradle.usage 'kotlin-api' and found compatible value 'java-api'.
      - Required org.jetbrains.kotlin.platform.type 'common' but no value provided.
  - Configuration ':testlib:debugApiElements' variant android-manifest:
      - Found artifactType 'android-manifest' but wasn't required.
      - Found com.android.build.api.attributes.BuildTypeAttr 'debug' but wasn't required.
      - Found com.android.build.api.attributes.VariantAttr 'debug' but wasn't required.
      - Found com.android.build.gradle.internal.dependency.AndroidTypeAttr 'Aar' but wasn't required.
      - Required org.gradle.usage 'kotlin-api' and found compatible value 'java-api'.
      - Required org.jetbrains.kotlin.platform.type 'common' but no value provided.
  - Configuration ':testlib:debugApiElements' variant android-renderscript:
      - Found artifactType 'android-renderscript' but wasn't required.
      - Found com.android.build.api.attributes.BuildTypeAttr 'debug' but wasn't required.
      - Found com.android.build.api.attributes.VariantAttr 'debug' but wasn't required.
      - Found com.android.build.gradle.internal.dependency.AndroidTypeAttr 'Aar' but wasn't required.
      - Required org.gradle.usage 'kotlin-api' and found compatible value 'java-api'.
      - Required org.jetbrains.kotlin.platform.type 'common' but no value provided.
  - Configuration ':testlib:debugApiElements' variant jar:
      - Found artifactType 'jar' but wasn't required.
      - Found com.android.build.api.attributes.BuildTypeAttr 'debug' but wasn't required.
      - Found com.android.build.api.attributes.VariantAttr 'debug' but wasn't required.
      - Found com.android.build.gradle.internal.dependency.AndroidTypeAttr 'Aar' but wasn't required.
      - Required org.gradle.usage 'kotlin-api' and found compatible value 'java-api'.
      - Required org.jetbrains.kotlin.platform.type 'common' but no value provided.</i>
```

Sync completes successfully with no warnings if you don't apply Kotlin Gradle plugin.

* Gradle version: 5.1.1
* Kotlin version: 1.3.31
* Android Studio 3.4.1
```
Build #AI-183.6156.11.34.5522156, built on May 1, 2019
JRE: 1.8.0_152-release-1343-b01 x86_64
JVM: OpenJDK 64-Bit Server VM by JetBrains s.r.o
macOS 10.14.5
```
