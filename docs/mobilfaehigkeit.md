# Mobilfähigkeit

Die zunehmende Nutzung von Unternehmens-Applikationen auf mobilen Geräten stellt besondere Anforderungen an die Entwicklung entsprechender Lösungen. Single Page Applications (SPA) eignen sich besonders gut für Szenarien, bei denen von einer Nutzung (auch) in mobilen Umgebungen ausgegangen wird oder den Anwendern nur geringe Bandbreiten zur Verfügung stehen. 

Kerngedanke ist dabei, dass durch die Nutzung einer einzigen Webpage (z.B. index.html) die Grundlage für einen vollständigen Client geladen wird. Der Client ist dabei eine vom Server unabhängige Einheit und wird zur Laufzeit basierend auf der Interaktion des Anwenders lokal dynamisch erweitert, ohne das eine Serverkommunikation für weitere Code-Teile notwendig ist. Bei dem sonst üblichen Wechsel von Webseiten im Rahmen einer Webanwendung im Webbrowser wird sämtliche clientseitige Präsentationslogik beendet und auf der nächsten Webseite neu begonnen. Ein solches Verhalten unterbindet länger laufende clientseitige Vorgänge sowie die Nutzung einer durchgängigen WebSocket-Verbindung. Dadurch können Wartezeiten reduziert werden und der Präsentationsfluß im Client bleibt unabhängig von einer schlechten/fehlenden Serveranbindung.

Der Sitzungszustand wird in SPA-Architekturen im Client gehalten. Dadurch werden auf den entsprechenden Servern keine unnötigen Ressourcen für die Zustandsspeicherung allokiert. Server-Backends können grundsätzlich zustandslos implementiert werden. Durch diese Art der Architektur gelingt es gerade in mobilen Szenarien mit vielen Anwendern eine effiziente Skalierung des Backends mit minimalen Ressourcen.

Bei einem SPA-Client beschränkt sich die Kommunikation mit dem Server auf die Abfrage/das Senden notwendiger Daten im schlanken JSON-Format. Overhead in der Kommunikation wird effizient vermieden. Statt bei jedem Request per Cookies Authentifizierungsinformationen mitzusenden, kann der SPA-Client selektiv für einzelne Kommunikationsvorgänge Tokens als Header-Informationen mitsenden. Dadurch wird ein minimaler Datenverbrauch und somit eine hohe Mobilfähigkeit erreicht.

Anwender wünschen sich - insbesondere bei mobilen Endgeräten - immer häufiger die Bereitstellung ihrer Anwendungssoftware in Form von Apps. Die zugehörigen Appstores ermöglichen eine unkomplizierte Installation von Annwendungen auf den Endgeräten und erleichtern das Einspielen von Updates. SPA-Clients lassen sich mit Hilfe von Wrappern wie Apache Cordova, nw.js oder Electron sehr leicht in solche Apps umwandeln. Diese Apps können dann auch auf Gerätehardware wie Kamera, GPS-Ortung oder Fingerprint-Sensor zugreifen. Auch eine Offlinefähigkeit durch die (Zwischen)speicherung von notwendigen Daten auf dem Gerät kann so erreicht werden.

SPA-Architekturen erlauben zusammengefasst besonders mobilfähige Clients für Unternehmen, die mit einer hohen Interaktivität und geringen Wartezeiten überzeugen können. Die Kommunikation mit Backends wird auf die reine Nutzdatenkommunikation beschränkt und erfolgt in der Regel zustandslos. Dadurch sind schlanke und skalierbare Backends möglich. Die umgesetzten Clients lassen sich leicht in native Apps umwandeln und können dann auch auf vorhandene Sensoren von Endgeräten zugreifen.