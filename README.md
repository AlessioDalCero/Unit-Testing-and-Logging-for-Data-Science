# Unit Testing and Logging for Data Science

In diesem Repository finden Sie:

-Ein Jupiter Notebook mit der Implementierung, dass auf der Musterlösung Logistische Regression aus dem Udemy- Kurs "Phython für Data Science, Maschinelles Lernen & Visualization" basiert.

-Testdaten

-Testdaten für den Unittest (Testfall 1) 'unittest_data_OK.txt' und 'unittest_data_N-OK.txt'

-Eine Konfigurationsdatei'environment.yml', die zur Ausführung benötigte Pakete enthält. 

Für die direkte Ausführung wird die Plattform myBinder https://mybinder.org/ verwendet.


 Wrapper Timer und Logger :

<script src="https://gist.github.com/orico/1bcffa51ccdd0c030ba4b7708d8656f3.js"></script>
    
Die Wrapper werden wiefolgt für folgende zwei Funktionen verwendet:



@my_logger
@my_timer
def logmodelFit():
   return logmodel.fit(X_train,y_train)
logmodelFit()



Eine Log-Datei "logmodelFit.log" wird ereugt, und erscheint links im Reiter. 





@my_logger
@my_timer
def logmodelPredict():
    return logmodel.predict(X_test)
predictions = logmodelPredict()





Bei der Ausführung des Notebooks wird die Laufzeit angezeigt.



Zwei Testfälle werden implementiert:

Testfall 1: Prüfung ob der Vorhersagewert predict() es Modells korrekt funktioniert.
Testfall 2: Prüfung der Laufzeit der Trainingsfunktion fit(). 




# Ergebnisse: 

# MyBinder 

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/AlessioDalCero/Unit-Testing-and-Logging-for-Data-Science/HEAD)
