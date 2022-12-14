# Lern-Bericht
Oltian Kadriu

## Einleitung

Wir lernen in diesem Modul wie man Applikationssicherheit in JSF implementiert.

## Was habe ich gelernt?

Ich habe gelernt, wie man XSS-Angriffe (XSS = Cross-Site-Scripting) verhindert.

## Beschreibung

XSS (Cross-Site-Scripting) ist eine Sicherheitslücke in Web-Anwendungen, die es Angreifern ermöglicht, bösartigen Code auf einer Webseite einzuschleusen und auszuführen. Um XSS-Angriffe in JSF (JavaServer Faces) zu verhindern, empfehle ich die Verwendung der <h:outputText>-Komponente anstelle der <h:outputLabel>-Komponente. Diese enthält standardmässig Escaping, um XSS-Angriffe zu verhindern.

Der Entwickler hat das Suchfeld eigentlich für solche Suchen entwickelt:
![grafik](https://user-images.githubusercontent.com/69577043/207427522-f5dc8d6d-190e-4469-9a0c-f14f3279c45b.png)

```xhtml
<!-- Das Escaping ist auf "false" und deshalb können es böse Menschen missbrauchen. -->
<h:outputText value="#{searchController.searchString}" escape="false" />
```

Hier kann man sehen, wie ein böser Mensch es tun könnte:
![grafik](https://user-images.githubusercontent.com/69577043/207428646-d997f717-414b-49b0-be32-7612b581ac24.png)
Um das zu verhindern, kann man ganz einfach, die Escape-Eigenschaft der <h:outputText>-Komponente von "false" auf "true" ändern:
```xhtml
<h:outputText value="#{searchController.searchString}" escape="true" />
```

Aber was macht eigentlich ```escape="true"```?
Wenn die Escape-Eigenschaft einer <h:outputText>-Komponente in JSF auf "true" festgelegt ist, wird der Inhalt der Komponente escapet, bevor er angezeigt wird. Dies bedeutet, dass Sonderzeichen wie <, > und & in eine lesbare Form konvertiert werden, sodass sie nicht als Code ausgeführt werden können.

In diesem Video kann man sehen, was passiert, wenn ```escape="true"```:

![escape true](https://user-images.githubusercontent.com/69577043/207435647-832a0569-384e-4ae3-8fb0-b326cf8d5338.gif)

Und wenn ```escape="false"``` ist:

![escape false](https://user-images.githubusercontent.com/69577043/207435751-1029fce2-7040-4929-9770-384210646b0d.gif)


## Verifikation

Von der Beschreibung können Sie lesen, dass ich verstanden habe, wie man XSS in JSF verhindern kann und verstanden habe, wie das Escaping funktioniert. Ebenfalls sieht man am Code, dass ich dies anwenden kann. Die Bilder bestätigen ebenfalls, dass ich weiss, wie ein normaler Benutzer ein Suchfeld benutzen würde und wie ein böser Mensch es benutzen würde. Die Codeabschnitte zeigen, dass man die Escape-Eigenschaft auf "true" haben sollte, sonst passiert genau das, was im Video gezeigt wird, wenn die Escape-Eigenschaft auf "false" ist.

# Reflektion zum Arbeitsprozess

Das Modul hat mir ganz OK gefallen und ich konnte die meisten Aufträge lösen, auch wenn wir die meiste Zeit zu Hause unterricht hatten.
Am allerersten Tag, wo wir das neue Modul begonnen haben, habe ich den Einstieg verpasst, da ich krank war und nicht anwesend. Dabei konnte ich diesen Stoff nicht nachholen, da ich die Aufträge nur mit den Präsentationen nicht lösen konnte...

**VBV**: Nächstes Mal könnte ich meine Lehrperson fragen, wenn ich fragen habe und den Einstieg verpasst habe, denn dieser ist am wichtigsten.
