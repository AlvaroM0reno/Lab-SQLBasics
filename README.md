
Introducción
En esta práctica de laboratorio, utilizará la files_for_lab/mysql_dump.sqlbase de datos. Cárguelo en Sequel Pro y allí encontrará una bankbase de datos que usaremos para el siguiente ejercicio.

Aquí practicaremos la selección y proyección de datos. Puedes terminar todas las preguntas solo con esas cláusulas:

SELECT
SELECT DISTINCT
FROM
WHERE
ORDER BY
LIMIT
Puede guardar sus soluciones en un archivo solutions.sql.

Instrucciones
Supongamos que las _idcolumnas son incrementales, lo que significa que los identificadores más altos siempre aparecen después de los identificadores más bajos. Por ejemplo, un cliente con un valor más alto client_idse unió al banco después de un cliente con un valor más bajo client_id.

Consulta 1
Obtenga los idvalores de los primeros 5 clientes district_idcon un valor igual a 1.

Resultado Esperado:

2
3
22
23
28
Consulta 2
En la clienttabla, obtenga un idvalor del último cliente donde sea district_idigual a 72.

Resultado Esperado:

13576
Consulta 3
Obtenga las 3 cantidades más bajas de la loantabla.

Resultado Esperado:

4980
5148
7656
Consulta 4
¿Cuáles son los valores posibles para status, ordenados alfabéticamente en orden ascendente en la loantabla?

Resultado Esperado:

A
B
C
D
Consulta 5
¿Cuál es el loan_idpago más alto recibido en la loantabla?

Resultado Esperado:

6312
Consulta 6
¿Cuál es el préstamo amountde los 5 account_ids más bajos de la loantabla? Mostrar el account_idy el correspondienteamount

Resultado Esperado:

#id     amount
2	    80952
19	    30276
25	    30276
37	    318480
38	    110736
Consulta 7
¿Cuáles son los account_ids con el préstamo más bajo amountque tienen un préstamo durationde 60 en la loantabla?

Resultado Esperado:

10954
938
10711
1766
10799
Consulta 8
¿Cuáles son los valores únicos de k_symbolen la ordertabla?

Nota: No debería haber un nombre de tabla order, ya que orderestá reservado de la ORDER BYcláusula. Tienes que usar comillas invertidas para escapar del ordernombre de la tabla.

Resultado Esperado:

LEASING
POJISTNE
SIPO
UVER
Consulta 9
En la ordertabla, ¿cuáles son los order_ids del cliente con el account_id34?

Resultado Esperado:

29445
29446
29447
Consulta 10
En la ordertabla, ¿cuáles account_idfueron responsables de los pedidos entre order_id29540 y order_id29560 (inclusive)?

Resultado Esperado:

88
90
96
97
Consulta 11
En la ordertabla, ¿cuáles son los montos individuales que se enviaron a ( account_to) id 30067122?

Resultado Esperado:

5123
Consulta 12
En la transtabla, muestre las trans_id, y de las 10 primeras transacciones de 793 en orden cronológico, de la más nueva a la más antigua date.typeamountaccount_id

Resultado Esperado:

3556468	981231	PRIJEM	78.6
233254	981216	VYDAJ	600
233104	981212	VYDAJ	1212
233248	981211	VYDAJ	851
233176	981207	VYDAJ	204
3556467	981130	PRIJEM	75.1
233395	981130	VYDAJ	14.6
233103	981112	VYDAJ	1212
233247	981111	VYDAJ	851
233175	981107	VYDAJ	204
Consulta 13
En la clienttabla, de todos los distritos con district_idmenos de 10, ¿cuántos clientes son de cada uno district_id? Muestra los resultados ordenados por district_iden orden ascendente.

Resultado Esperado:

1	663
2	46
3	63
4	50
5	71
6	53
7	45
8	69
9	60
Consulta 14
En la cardtabla, ¿cuántas tarjetas existen para cada uno type? Clasifica el resultado empezando por el más frecuente type.

Resultado Esperado:

classic	659
junior	145
gold	88
Consulta 15
Usando la loantabla, imprima los 10 primeros account_idsegún la suma de todos los montos de sus préstamos.

Resultado Esperado:

7542	590820
8926	566640
2335	541200
817	    538500
2936	504000
7049	495180
10451	482940
6950	475680
7966	473280
339	    468060
Consulta 16
En la loantabla, recupere el número de préstamos emitidos para cada día, antes de (excluido) 930907, ordenados por fecha en orden descendente.

Resultado Esperado:

930906	1
930803	1
930728	1
930711	1
930705	1
Consulta 17
En la loantabla, para cada día de diciembre de 1997, cuente el número de préstamos emitidos para cada duración única del préstamo, ordenados por fecha y duración, ambos en orden ascendente. Puede ignorar los días sin préstamos en su salida.

Resultado Esperado:

971206	24	1
971206	36	1
971208	12	3
971209	12	1
971209	24	1
971210	12	1
971211	24	1
971211	48	1
971213	24	1
971220	36	1
971221	36	1
971224	60	1
971225	24	1
971225	60	1
Consulta 18
En la transtabla, para account_id396, sume la cantidad de transacciones para cada tipo ( VYDAJ= Saliente, PRIJEM= Entrante). Su salida debe tener el account_id, el typey la suma de la cantidad, denominados como total_amount. Ordenar alfabéticamente por tipo.

Resultado Esperado:

396	PRIJEM	1028138.6999740601
396	VYDAJ	1485814.400024414
Consulta 19
Del resultado anterior, traduzca los valores de typeal inglés, cambie el nombre de la columna a transaction_type, redondee total_amounthacia abajo a un número entero

Resultado Esperado:

396	INCOMING	1028138
396	OUTGOING	1485814
Consulta 20
A partir del resultado anterior, modifique su consulta para que devuelva solo una fila, con una columna para el monto entrante, el monto saliente y la diferencia.

Resultado Esperado:

396	1028138	1485814	-457676
Consulta 21
Continuando con el ejemplo anterior, clasifique los 10 primeros account_idsegún su diferencia.

Resultado Esperado:

9707	869527
3424	816372
3260	803055
2486	735219
1801	725382
4470	707243
3674	703531
9656	702786
2227	696564
6473	692580

