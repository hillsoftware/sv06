Sovol SV06 2.1.x bugfix build

Das Eeprom sollte zurückgesetzt werden, wenn Sie eine wichtige Firmware ändern, 
aber Sie können das Eeprom auch konfigurieren/erweitern/initialisieren und zurücksetzen, wenn Sie möchten.
Verwenden Sie zwei identische Objekte auf dem Bett, eines unter jeder Seite des Portals und senken Sie das Portal von Hand ab, 
verwenden Sie nicht die Motoren, um es abzusenken, die Stepper müssen deaktiviert oder der Drucker ausgeschaltet werden.
Gehen Sie zu Motion / Homing und wählen Sie Auto Home. Beobachten Sie den Referenziervorgang. Die X-Achse sollte 
ganz nach links gehen und an der linken Seite des Rahmens anstoßen. Die Y-Achse sollte ganz nach hinten gehen und 
gegen die Rückseite des Rahmens stoßen. Wenn eine der beiden Achsen nicht ganz durchläuft oder Schleifgeräusche macht, 
ist die Empfindlichkeit zu hoch bzw. zu niedrig. Wenn Sie ein Problem damit haben, dass die X-Achse nicht ganz nach links fährt, 
ist die sensorlose Referenzfahrt für die X-Achse zu empfindlich. Wenn sie laut gegen die linke Seite schleift, 
ist sie ebenfalls nicht empfindlich genug. Gehen Sie zu Konfiguration / Erweitert / TMC-Treiber / Sensorlose Referenzfahrt.  
Gehen Sie zu der Achse, die Sie optimieren möchten (X oder Y). Wenn Ihre X-Achse anhält, bevor sie die linke Seite trifft, 
sind Sie zu empfindlich auf X. Senken Sie also den X-Wert um 5 und versuchen Sie die Referenzfahrt erneut. 
Wenn Ihre X-Achse zu sehr schleift, z. B. auf der linken Seite, sind Sie empfindlich genug, also erhöhen Sie den X-Wert um 5. 
Wenden Sie dasselbe Verfahren für Y an, wenn es Probleme gibt. Sobald Sie die Werte nach Ihrem Geschmack eingestellt haben, 
sollten Sie die Einstellungen speichern, damit sie bei einem Neustart erhalten bleiben.
Autotune PID.  Konfiguration / Erweitert / Temperaturen / PID Autotune Extruder (auf Fertigstellung warten). 
Beachten Sie, dass dies eine Weile dauern kann.
Die PID-Abstimmung ist abgeschlossen, wenn die Heizeinheit auf Raumtemperatur abkühlt.
Speichern Sie hier die Einstellungen für den Fall eines Neustarts.
Autotune Bed PID Configuration / Advanced / Temperatures / PID Autotune Bed (warten Sie auf das Ende)
Einstellungen speichern ist eine gute Idee im Falle eines Neustarts
Bevor Sie einen der folgenden Schritte durchführen. Stellen Sie sicher, dass KEIN Filament aus der Düse hängt. 
Das zuvor durchgeführte Autotune des Extruders kann dazu führen, dass Filament herausquillt. 
Dies kann zu fehlerhaften Kalibrierungen führen, wenn Sie einen Z-Offset oder X-Twist durchführen, 
da das trockene Filament den Eindruck erweckt, dass Sie sich näher am Bett befinden, als es tatsächlich der Fall ist!
Gehen Sie zu Konfiguration/Erweitert/Sonde Offsets /Z Offset Wizard (No X-Twist) und kalibrieren Sie Ihren Z-Offset. 
Speichern Sie die Einstellungen.

Wenn Sie die UBL-Version heruntergeladen haben, führen Sie die folgenden Schritte aus:

Gehen Sie zu Bewegung / Unified Bed Leveling / UBL Mesh Wizard
Lassen Sie den UBL alle Punkte sondieren, die er kann. Es wird nicht möglich sein, alle 100 Punkte zu sondieren. Das ist normal.
Die Einstellungen sollten automatisch gespeichert werden, wenn UBL fertig ist, aber Sie können auch selbst speichern, wenn Sie möchten.

Wenn Sie die bi-lineare Version heruntergeladen haben, führen Sie die folgenden Schritte aus:

Gehen Sie zu Bewegung / Bettnivellierung / Bett nivellieren
Lassen Sie alle 25 Punkte abtasten
Wenn Sie fertig sind, speichern Sie die Einstellungen, um die Netzdaten zu speichern.

Die folgenden Schritte gelten für UBL- oder bi-lineare Versionen:

Machen Sie jetzt einen Testdruck, bevor Sie x-twist ausprobieren.   
So können Sie feststellen, ob die UBL- oder bi-lineare Nivellierung ausreicht, 
um Ihre Probleme mit den ersten Schichten usw. zu kompensieren, bevor Sie x-twist ausprobieren. 
Vergewissern Sie sich, dass Sie den richtigen Start-G-Code haben, um das UBL- oder bi-lineare Netz wie unten beschrieben zu verwenden.
Wenn Ihr Druck gut ist.  Herzlichen Glückwunsch und viel Spaß beim Drucken.
Wenn das nicht genug geholfen hat, führen Sie X-Twist aus. 
Konfiguration / Erweitert / Probe Offsets / X-Twist
WICHTIG! Führen Sie Ihr UBL- oder bi-lineares Netz nach dem X-Twist erneut aus 
(die Verdrehung verändert nicht die bestehenden Netzdaten, sondern nur die zukünftigen Sondenpunkte, 
während die UBL- oder bi-lineare Nivellierung ihre Arbeit erledigt).
Speichern Sie die Einstellungen und machen Sie einen Testdruck.
Wenn Ihr Druck gut ist, viel Spaß beim Drucken. Wenn nicht, besuchen Sie die SV06 Facebook Gruppe und lassen Sie es uns wissen. 
Bilder, Details, Daten usw. können uns dabei helfen, Ihr Problem zu identifizieren und zu sehen, ob wir die Firmware verbessern können.
Wenn Sie feststellen, dass UBL und Bi-Linear für Ihr Gerät nicht ausreichen, 
können Sie auch die Version mit manuellem Netz herunterladen. 
Diese funktioniert wie die bi-lineare Version, aber Sie verwenden manuell das Papier oder die Fühlerlehre mit der Düse für die 5x5-Maschen.
Achten Sie darauf, danach zu speichern. 
Diejenigen, die mit der Standard-Firmware oder meiner UBL- oder bi-linearen Version Probleme hatten, 
eine gute erste Schicht zu erhalten, haben mit der manuellen Mesh-Version ihr Problem gelöst. 
Allerdings ist dies ein manueller Prozess und nimmt die Sonde aus dem Bild.

