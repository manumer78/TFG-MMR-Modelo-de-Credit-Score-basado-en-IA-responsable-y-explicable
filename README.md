# TFM-MMR-Modelo-de-Credit-Score-basado-en-IA-responsable-y-explicable
Repositorio para el código utilizado en el TFG del Grado en Ciencia de Datos Aplicada de la UOC.

El objetivo del TFG es desarrollar un modelo de machine learning (ML) para evaluar la solvencia de los solicitantes de crédito, también conocidos como modelos de credit score, siguiendo las premisas de la IA Responsable, poniendo especial énfasis en la explicabilidad del modelo. Esto último enlaza el proyecto con el concepto de IA Explicable (XAI por sus siglas en inglés).

En el ficheros del repositorio se va a desarrollar todo el código Python necesario para realizar las diferentes fases técnicas del proyecto. Estas incluyen las siguientes tareas.

    - Análisis exploratorio de datos (EDA)
    - Ingeriería de características y preparación del dataset para su procesamiento.
    - Selección e implementación del modelo de ML para credit score.
    - Implementación de la explicabilidad para facilitar su interpretabilidad.

El conjunto de datos seleccionado para realizar el proyecto es Home Credit Default Risk, que se puede encontrar en el siguiente enlace: 
https://www.kaggle.com/c/home-credit-default-risk/overview. 

El conjunto de datos está formado por los siguientes ficheros:

    - application_train.csv – Información demográfica y financiera de los clientes que solicitaron un préstamo (incluye 
    la variable objetivo TARGET, donde 1 indica que el cliente incumplió el pago y 0 que no).
    
    - application_test.csv – Mismo formato que application_train.csv, pero sin la columna TARGET (para predicciones).
    
    - bureau.csv – Historial crediticio de los clientes con otras entidades financieras.
    
    - bureau_balance.csv – Estados mensuales de los créditos en bureau.csv.
    
    - previous_application.csv – Información sobre préstamos previos solicitados por los clientes.
    
    - POS_CASH_balance.csv – Información de préstamos en punto de venta y de efectivo.
    
    - installments_payments.csv – Historial de pagos de los clientes en préstamos anteriores.
    
    - credit_card_balance.csv – Datos de comportamiento de tarjetas de crédito anteriores.

Para el desarrollo del proyecto, se generará a partir de los datos de los ficheros anteriores un conjunto de datos con todas aquellas variables predictoras que se puedan considerar relevantes. En relación a los ficheros se ha de tener en cuenta lo siguiente:

    - La base del conjunto de datos que se usará en el modelo son los ficheros application_train y application_test, 
    ya que contienen variables relacionadas con la solicitud y con el cliente que la realiza.
    - Los ficheros bureau y bureau_balance son ficheros con información de otros créditos del cliente en otras entidades, 
    que permitirán inferir información relevante de su comportamiento crediticio que podrá ser integrada en el conjunto de datos final.
    - Los ficheros previous_application, POS_CASH_balance, installments_payments y credit_card_balance son ficheros con información 
    de otros créditos del cliente en la entidad, que permitirán inferir información relevante de su comportamiento crediticio que 
    podrá ser integrada en el conjunto de datos final.

Antes de continuar, se han de tener en cuenta que en los ficheros application_train y application_test se está registrando una solicitud de crédito por cliente. No existen más de dos solicitudes del mismo cliente, y si las hay no existe forma de relacionarlas. Este punto es relevante ya que toda la información recopilada en los ficheros de bureau y de solicitudes previas en la misma entidad se relacionan por el identificador del prestamo, que es a su vez el indicador del cliente.
