# 001: Flutter Doctor: Unable to determine bundled Java Version
![[Pasted image 20251017222912.png]]

>[!tip] Solution
>1. Determine which version Android Studio
>2. Find out Android Studio configuration JDK Path
>```bash
>C:\Program Files\Android\Android Studio\jbr
>```
>3. Configuration Flutter SDK
>```bash
>flutter config --jdk-dir "C:\Program Files\Android\Android Studio\jbr"
>```
>

