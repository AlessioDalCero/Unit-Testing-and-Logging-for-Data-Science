# Unit Testing and Logging for Data Science

In diesem Repository finden Sie:

-Ein Jupiter Notebook mit der Implementierung, dass auf der Musterlösung Logistische Regression aus dem Udemy- Kurs "Phython für Data Science, Maschinelles Lernen & Visualization" basiert.

-Testdaten

-Testdaten für den Unittest (Testfall 1) 'unittest_data_OK.txt' und 'unittest_data_N-OK.txt'

-Eine Konfigurationsdatei'environment.yml', die zur Ausführung benötigte Pakete enthält. 

Für die direkte Ausführung wird die Plattform myBinder https://mybinder.org/ verwendet.


 Wrapper Timer und Logger :




    from functools import wraps


    def my_logger(orig_func):

    import logging
    logging.basicConfig(filename='{}.log'.format(orig_func.__name__), level=logging.INFO)

    @wraps(orig_func)
    def wrapper(*args, **kwargs):
        logging.info(
            'Ran with args: {}, and kwargs: {}'.format(args, kwargs))
        return orig_func(*args, **kwargs)

    return wrapper


    def my_timer(orig_func):
    import time

    @wraps(orig_func)
    def wrapper(*args, **kwargs):
        t1 = time.time()
        result = orig_func(*args, **kwargs)
        t2 = time.time() - t1
        print('{} ran in: {} sec'.format(orig_func.__name__, t2))
        return result

    return wrapper





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
