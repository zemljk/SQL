Есть таблица данных RAW_DATA 
•	"LOAD_ID" VARCHAR2(32 CHAR) NOT NULL ENABLE, 
•	"MACROREGION" VARCHAR2(80 CHAR), 
•	"SUBSCRIBER_BASE_TYPE" VARCHAR2(80 CHAR), 
•	"CONCERN_ACCOUNT" VARCHAR2(80 CHAR), 
•	"COMPANY_CODE" VARCHAR2(80 CHAR), 
•	"MICROREGION" VARCHAR2(80 CHAR), 
•	"PROGRAM" VARCHAR2(80 CHAR), 
•	"FISCAL_YEAR" NUMBER, 
•	"PERIOD" NUMBER, 
•	"CURRENCY_AMOUNT" NUMBER
Она наполняется ежемесячно 5 числа. Причем в ней приходят все прошедшие месяца за отчетный год. Т.е., например, данные которые придут в апреле могут содержать скорректированные данные января.
5 февраля – январь (LOAD_ID = ‘20220205’)
5 марта – январь, февраль (LOAD_ID = ‘20220305’)
5 апреля – январь, февраль, март (LOAD_ID = ‘20220405’)
…
5 декабря - январь, … , ноябрь (LOAD_ID = ‘20221105’)
Вопрос: 5 апреля надо проверить изменились ли данные января и февраля по сравнению с предыдущей загрузкой. 


Немного информации для пояснения столбцов

·       "LOAD_ID" VARCHAR2(32 CHAR) NOT NULL ENABLE,      - ID загрузки (уникальное для каждой загрузки)

·       "MACROREGION" VARCHAR2(80 CHAR),                              - регион по которому пришли данные (может измениться)

·       "SUBSCRIBER_BASE_TYPE" VARCHAR2(80 CHAR),            - тип абонента (может измениться)

·       "CONCERN_ACCOUNT" VARCHAR2(80 CHAR),                   - счет концерна (может измениться)

·       "COMPANY_CODE" VARCHAR2(80 CHAR),                          - код компании (может измениться)

·       "MICROREGION" VARCHAR2(80 CHAR),                                - региональное отделение (может измениться)

·       "PROGRAM" VARCHAR2(80 CHAR),                                        - проект (может измениться)

·       "FISCAL_YEAR" NUMBER,                                                           - год (по этому полю отсекаются все записи не относящиеся к текущему году)

·       "PERIOD" NUMBER,                                                                      - календарный номер месяца (по нему нужно фильтровать январь и февраль) (может измениться)

·       "CURRENCY_AMOUNT" NUMBER                                           – сумма (может измениться)
