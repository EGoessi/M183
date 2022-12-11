# Lern-Bericht
Elias Gössi

## Einleitung
Wir haben das Modul 183 bearbeitet. Das Thema dieses Moduls war Applikationssicherheit.

## Was habe ich gelernt?
Ich habe in diesem Modul gelernt wie man die Angriffsfläche so klein wie möglich hält. Eines der Probleme ist Direct Access.  


## Beschreibung
Mit Direct Acces hat man direkten Zugriff auf die geschütze Ressourcen. Falls dies der Fall ist, ist der direkte Zugriff auf Ressourcen nicht überwacht.
So besteht das Risiko, das ein unberechtiger Benutzer Zugriff auf Daten und Funktionen hat. 
Jeder direkte Zugriff auf Dateien in einem geschützten Bereich soll auf die Berechtigung geprüft werden. 
Das kann man zum Beispiel verhindern, indem man Filter einbaut.

Der erste Schritt ist es den Filter zu erstellen. 
Das ist sehr simple, indem man im NetBeans das bestimmte Projekt öffnet und im Source Package einen neuen Filter erstellt.

Danach muss der Filter konfiguriert werden. 

![image]()

Jedoch wird die eigentliche Filtrierung im doFilter vorgenommen.
```java
@inject
Login Controller loginController;
public void doFilter(ServletRequest request, ServletResponse response,
FilterChain chain) throws IOException, ServletException {
final HttpServletRequest httpRequest = (HttpServletRequest) request;
final HttpServletResponse httpResponse = (HttpServletResponse) response;
final String loginURL = httpRequest.getContextPath() + "/index.xhtml";
// this is where the magick happens
if (loginController.getUser() == null) {
httpResponse.sendRedirect(loginURL);
}
chain.doFilter(request, response);
}
```
(Screenshots von "183 Zusammenfassung", da die es sehr gut erklären)

## Verifikation

Die Bilder zeigen Schritt für Schritt wie und wo man den Filter erstellen muss. Zudem auch welche Änderungen am Code vorgenommen werden müssen.

# Reflektion zum Arbeitsprozess

Bei dem Modul sind die meisten Sachen nicht so gut gegangen. Ich habe oft länger an einigen Aufgaben gebraucht, da es nicht funktioniert hat oder 
ich es nicht verstanden habe. Jedoch gab es auch einfachere Themen wie das einbauen von Filtern. Aber im gesamten hatte ich viele Schwierigkeiten
welche ich mit Hilfe von Klassenkameraden oder den PowerPoint lösen konnte.

**VBV**: 
Die Theorie sollte ich mehrmals lesen und auch komplett verstehen. 
Ansonsten alle offenen Fragen am Anfang klären anstatt abzuwarten. 
