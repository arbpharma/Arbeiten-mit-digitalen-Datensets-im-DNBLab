Dieses Repository widmet sich der Erforschung und Analyse der Entwicklung von Musik über verschiedene Zeitperioden. Ziel des Projekts ist es, Muster, Trends und Einflüsse in der musikalischen Entwicklung zu untersuchen. Die Daten können unter folgenden Link eingesehen werden: https://portal.dnb.de/opac.htm?method=showShortList&currentPosition=17&currentResultId=cod%3Dnt%26any%26onlinefree%26scores

Analyse-Pipeline der Deutschen Nationalbibliothek (DNB)

🔧 Übersicht

Diese Analyse-Pipeline dient dazu, Daten aus der Deutschen Nationalbibliothek (DNB) effizient zu verarbeiten. Sie umfasst:

Automatisiertes Herunterladen von PDFs von der DNB-Webseite.

Textextraktion (direkt oder mittels OCR) aus den PDFs.

Textanalyse und Visualisierung der Ergebnisse.

🔄 Ablauf der Pipeline

1. PDF-Downloader

Datei: 1_dnb_pdf_downloader.ipynb

Funktion:
Automatisches Herunterladen von PDFs von der Webseite der DNB.

Details:

Die Webseite wird mit Selenium, einer Automatisierungssoftware, navigiert.

Das Programm klickt auf Download-Links und speichert die PDFs lokal.

Download-Beschränkung: Standardmäßig werden die ersten 100 PDFs heruntergeladen, um Speicherplatz zu sparen.

Voraussetzungen:

Selenium WebDriver mit Google Chrome.

Download-Verzeichnis: Standardordner ist pdf.

2. PDF-Leser: Textextraktion und OCR

Datei: 2_pdf_reader_base_code.ipynb

Funktion:
Extrahiert Texte und Bilder aus den heruntergeladenen PDFs.

Ablauf:

Direkte Textextraktion:
Wenn der Text digital im PDF enthalten ist, wird er direkt ausgelesen.

Texterkennung (OCR):
Wenn der Text nicht lesbar ist (z. B. bei eingescannten Dokumenten), wird OCR (Optical Character Recognition) verwendet.

Technologien:

PyMuPDF (Fitz): Für direkte Textextraktion.

Pytesseract: Für OCR auf Bildern.

EasyOCR: Eine genauere OCR-Alternative (ressourcenintensiv).

3. Textanalyse und Visualisierung

Datei: 3_pdf_analyse.ipynb

Funktion:
Analysiert die extrahierten Texte und erstellt eine Wortwolke, um die häufigsten Begriffe zu visualisieren.

Ablauf:

Entfernt irrelevante Wörter (wie „der“, „und“) mithilfe einer Liste deutscher Stopwörter.

Erstellt aus dem bereinigten Text eine Wortwolke mit häufigen Begriffen.

Technologien:

WordCloud: Zur Visualisierung.

Matplotlib: Zur Darstellung der Wortwolke.

NLTK: Für die Stopwörterliste.

🚀 Wie starte ich die Pipeline?

Voraussetzungen

Python 3.9 oder höher

Installierte Python-Bibliotheken:

selenium

webdriver-manager

requests

fitz (PyMuPDF)

pytesseract

easyocr

nltk

matplotlib

wordcloud

Tesseract OCR:

Installieren Sie Tesseract von der offiziellen Webseite: https://github.com/tesseract-ocr/tesseract.

Stellen Sie sicher, dass der Pfad zu Tesseract in der Datei korrekt angegeben ist.

Anleitung

Klonen Sie dieses Repository:

git clone <repository-url>

Installieren Sie die Abhängigkeiten:

pip install -r requirements.txt

Führen Sie die Dateien in der folgenden Reihenfolge aus:

1_dnb_pdf_downloader.ipynb ➔ Lädt die PDFs herunter.

2_pdf_reader_base_code.ipynb ➔ Extrahiert Texte und Bilder.

3_pdf_analyse.ipynb ➔ Analysiert Texte und erstellt eine Wortwolke.

🔎 Wichtige Hinweise

Speicherplatz:
Das komplette PDF-Set kann sehr groß sein (bis zu 174 GB). Laden Sie nur so viele Dateien herunter, wie Sie benötigen.

Performance:
Die OCR-Erkennung (insbesondere EasyOCR) ist ressourcenintensiv. Führen Sie das Skript auf einem leistungsfähigen Rechner aus.

Datenquellen:
Die verwendeten PDFs stammen von der Webseite der Deutschen Nationalbibliothek und unterliegen deren Nutzungsbedingungen.

📊 Beispiel: Ergebnis der Wortwolke

Nach der Analyse sehen Sie eine grafische Darstellung der häufigsten Begriffe in den PDF-Inhalten:



🛠️ Support

Wenn Sie Fragen oder Probleme haben, melden Sie sich bei uns über das Issue-Tracking-System oder per E-Mail.

Viel Erfolg bei der Analyse!
