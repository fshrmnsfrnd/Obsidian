---
Fach: "[[AWM]]"
Thema:
  - "[[Android]]"
---
# Compile SDK Version 
---
Die Compile SDK-Version ist die **Android-Version**, in der Sie Code schreiben. Wenn Sie 8.1 wählen, können Sie Code mit allen APIs in Version 27 schreiben. Wenn Sie Android 4.4 auswählen, können Sie Code nur mit den APIs schreiben, die in API Level 19 oder früher vorliegen.

# Minimale SDK-Version 
---
Android-Betriebssystemversionen sind abwärtskompatibel. Wenn Ihre `minSdkVersion` beispielsweise auf Android Version 4.4 eingestellt ist, kann Ihre Anwendung auf Android zurück bis Version 4.4 laufen. Der Vorteil der Wahl des 4.4-Frameworks besteht darin, dass Ihre Anwendung einem viel größeren Marktanteil ausgesetzt ist. Außerdem läuft sie auch auf allen zukünftigen Versionen. Sie sollten die `minSdkVersion` auf die älteste Version von Android festlegen, die Sie unterstützen möchten.

Die `minSdkVersion` ist technisch optional, aber Sie sollten sie immer einstellen! Wenn Sie nicht wissen, worauf Sie es festlegen sollen, nehmen Sie die Version Ihrer Compile SDK

Auf alle Fälle sollten Sie Ihre App auf jeder unterstützten Plattform testen!

Der Google Play Store entscheidet basierend auf Ihrer `minSdkVersion`, welchen Nutzern Ihre App angezeigt wird.

# Ziel-SDK-Version 
---
Diese Einstellung wird oft missverstanden. Die `targetSdkVersion` legt fest, bis zu welcher **maximalen Version** die App einsetzbar ist. Stellen Sie die `targetSdkVersion` wenn möglich auf die Version von Android ein, die Ihre App maximal unterstützt. Dadurch stellen Sie sicher, dass das Verhalten dieser Version übernommen wird. Kommt nun eine neue Version von Android herauskommt, sollten Sie die `targetSdkVersion` Ihrer Projekte auch auf die diese Android-Version aktualisieren und Ihre App testen, und eventuelle Probleme beheben. Wenn Sie das nicht tun, erhalten Sie nur das Verhalten, das für die Abwärtskompatibilität vorgesehen ist. 
Die aktuelle Android Version ist 16.0 mit API Level 36.0. (09/2025)

