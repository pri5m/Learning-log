# Gradle lombok

Underneath the buildscript paste in:
```
plugins {
	id 'io.franzbecker.gradle-lombok' version '1.14'
}
```

Then paste this in above the dependencies:
```
lombok {
    version = '1.18.2'
    sha256 = ""
}
```

Make sure that the compile only lombok in the deperndencies is commented out
