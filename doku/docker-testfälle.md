#  Docker Testfälle

## 01-Apache funktionalität
#### Testbeschreibung:
1. Browser öffnen
2. localhost:8080

 Erwartet| Ergebnis|
|--|--|
| Apache antwortet mit webseite | Apache antwortet mit webseite |

## 01-Wordpress funktionalität
#### Testbeschreibung:
1. Apache antwortet mit webseite
2. wordpress url aufrufen

 Erwartet| Ergebnis|
|--|--|
| Wordpress setup wird angezeigt | Hat nicht funktioniert |

## 03-MySQL funktionalität
#### Testbeschreibung:
1. Wordpress setup
2. Datenbank konfigurieren


 Erwartet| Ergebnis|
|--|--|
| Wordpress Akzeptiert DB credentials | MySQL konnte installiert werden wordpress aber nicht |

## 03-Volle funktionalität
#### Testbeschreibung:
1. in wordpress
2. Admin login
3. Versuchen, Blogpost zu erstellen


 Erwartet| Ergebnis|
|--|--|
| Blogpost wird erstellt und kann angezeigt werden | Hat nicht Funktioniert |

