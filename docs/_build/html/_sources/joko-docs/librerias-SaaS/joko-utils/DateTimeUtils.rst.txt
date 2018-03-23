DateTimeUtils
-------------
Esta clase contiene un montón de utilidades para trabajar con fechas y tiempos

.. data:: Date now()
	
	Retorna la fecha y tiempo actual.

.. data:: Date today()

	Retorna la fecha y tiempo del día actual.

.. data:: int getCurrentMonth()
	
	Retorna el mes actual como un número.

.. data:: int getCurrentYear()

	Retorna el año actual como un número.

.. data:: Integer yearsBetween(Date fromDate, Date toDate) 	

	Retorna un objeto con la cantidad de años entre las dos fechas proveídas.

.. data:: Integer daysBetween(Date fromDate, Date toDate)

	Retorna un objeto con la cantidad de días entre las dos fechas proveídas.

.. data:: Date firstDayOfMonth()

	Retorna la fecha del primer día del mes actual (Con tiempo puesto en 0 en todos los campos).

.. data:: Date lastDayOfMonth()
	
	Retorna la fecha del último día del mes actual (Con tiempo puesto en 0 en todos los campos).

.. data:: Integer daysTillEndOfMonth()

	Retorna un objeto con los días que faltan para el final del mes actual.

.. data:: Date subtractDaysFromDate(Date date, int days)

	Retorna la fecha resultante al restar la cantidad de días proveídos a la fecha proveída (Con tiempo puesto en 0 en todos los campos).

.. data:: Date subtractMonthFromDate(Date date, int months)

	Retorna la fecha resultante al restar la cantidad de meses proveídos a la fecha proveída (Con tiempo puesto en 0 en todos los campos).

.. data:: Boolean currentTimeWithin(Integer from, Integer to)

	Retorna ``True`` sólo si es que el tiempo actual se encuentra entre los tiempos proveídos.

.. data:: Boolean currentTimeBefore(Integer time)

	Retorna ``True`` sólo si es que el tiempo actual se encuentra antes que el tiempo proveído.

.. data:: Boolean currentTimeAfter(Integer time)
	
	Retorna ``True`` sólo si es que el tiempo actual se encuentra después que el tiempo proveído.

.. data:: GregorianCalendar calendarFromHour(final String hh)

	Retorna un calendario del tipo GregorianCalendar creado usando la hora proveída con el formato ``HH`` con valor entre ``00`` y ``29``.

.. data:: Date dateFromHourMinSec(final String hhmmss)

	Retorna una fecha sumando la fecha actual con el tiempo pasado en el formato ``HH:MM:SS`` donde la hora esta entre ``00`` y ``29`` y los minutos y segundos entre ``00`` y ``59`` (De poner más de 23 horas se ajustara el día de la fecha).

.. data:: Boolean isDay(DayOfWeek day)

	Retorna ``True`` si el día de la semana actual es igual al proveído (Mirar tipo DayOfWeek definido en java.time).

.. data:: Date shiftDate(Date date, Integer seconds, Integer minutes, Integer hours, Integer days, Integer months, Integer years, Boolean delay)

	Retorna el tipo Date proveído (Fecha y Tiempo) sumándole (Si delay es ``False``) o restándole (Si delay es ``True``) los demás campos proveídos con sus respectivos campos del tipo Date.

.. data:: Date shiftDate(Date date, Integer miliseconds, Integer seconds, Integer minutes, Integer hours, Integer days, Integer months, Integer years, Boolean delay)

	Retorna el tipo Date proveído (Fecha y Tiempo) sumándole (Si delay es ``False``) o restándole (Si delay es ``True``) los demás campos proveídos con sus respectivos campos del tipo Date.

.. data:: Date parseDate(String fechaString)	

	Usando el formato definido en el string DATE_TIME_FORMAT de la clase JokoConstants se analiza el string proveído para retornar un objeto del tipo Date con los datos obtenidos del string, por defecto el formato definido por DATE_TIME_FORMAT es ``dd/MM/yyyy HH:mm:ss`` (Day, Month, Year, Hour, Minute, Second).

.. data:: Date getDateUntilFriday()

	Retorna la fecha y tiempo hasta el viernes siguiente.

+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Heya 	                                                                                                                                                                                                            |
+===================================================================================================================================================================================================================+
| ikpbnheofikbnpoeikfrsdnjvmpoikrnhtjfgmvolijkjntfsodgilkvnoetiklrfjdgmvpiketnjhfbopikljtrnmfoglikvjnmetos jvlkdjsavlkxnjvoeikjsldnmvoilknheofrsdklgjnfmcoierkjlvmovieklrjngvonroeinsoifbnoaidnboiadfnboiadnfboi    |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+


.. data:: Date getDateUntilEndOfMonth()

	Retorna la fecha y tiempo hasta el siguiente mes.

.. data:: Date getDateUntilEndOfYear()

	Retorna la fecha y tiempo hasta el año siguiente.
