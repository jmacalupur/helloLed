# helloLed
Primer proyecto de Arduino: Encender y apagar un Led con Arduino.


# Objetivo 

Entender cómo se programa en Arduino y cuál es la forma correcta de ensamblar las partes de un sistema básico.


# ¿Qué es Arduino?

Arduino es una tarjeta o placa de prototipos flexibles que te permite crear proyectos interactivos. Viene acompañado de su propio IDE en el cual puedes personalizar cualquier programa que tengas en mente. 


# Materiales y Equipos

 - Laptop con el IDE Arduino instalado (puedes descargarlo desde [aquí](https://www.arduino.cc/en/Main/Software))
 - Protoboard 
 - Placa Arduino UNO
 - Cables macho
 - LED
 - Resistencia de 220Ω
 - Cable USB-B

 Nota: de no tener un arduino puedes hacer el diseño desde www.tinkercad.com

# Procedimiento

1. Para este paso, tenemos que basarnos en el diseño de lo que vamos a ensamblar y programar. En este caso, es un LED que encenderá 1 segundo y se apagará 1 segundo. 

2. Luego, procedemos a armar el sistema en el hardware. Usaremos una maquetación virtual en www.tinkercad.com:

<<<<<<< HEAD
[]!()

Aunque también, si tienes un arduino a la mano puedes ensamblarlo:

[]!()

3. A fin de evitar que el LED se queme deibo a la alta intensidad de corriente que recibiría, se ha optado por colocar una resistencia de 220Ω. 

	¿Cómo lo calculé?. Pues por medio de la Ley de Ohm:
=======
[]!(https://github.com/jmacalupur/helloLed/blob/master/01arduinoTinkerCad.png)

Aunque también, si tienes un arduino a la mano puedes ensamblarlo:

[]!(https://github.com/jmacalupur/helloLed/blob/master/02fotoArduinoFisico.JPG)

Si hacemos un zoom de la imagen podemos ver la conexión de la Protoboard
[]!(https://github.com/jmacalupur/helloLed/blob/master/03arduinoZoom.png)


3. A fin de evitar que el LED sufra un daño debibo a la alta intensidad de corriente que recibiría, optemos por colocar una resistencia de 220Ω. Pero, ¿Cómo lo calculé?. Pues por medio de la Ley de Ohm:
>>>>>>> develop

	V = I x R

	Siendo:
	V = diferencia de voltaje (en Volts)
	I = Intensidad de corriente (en Amperios o Ampère)
	R = Resistencia (en Ohm)

	Detallemos el ejercicio para calcular la resistencia ideal para este caso:

	El voltaje que sale del Arduino hacia la placa es de 5V. Además el Led genera una caída de volate de  2V. Por lo tanto la diferencia es de 3V.

	V = 5 - 2 = 3V

	La intensidad de corriente que requiere el LED según sus especificaciones técnicas varía mucho, y depende del fabricante, sin embargo se tiene que el valor máximo promedio que soporta es de 20mA. Esto quiere decir que optando por un valor menor (considerando un % de seguridad), consideraré sólo para este ejercicio un valor de 17mA.  

	A = 17mA = 0.017 A

	Una vez teniendo los valores, procedemos a calcular la resistencia:

	3 = 0.017 x R
	R = 176Ω

	Como este valor no es comercial, y viendo las resistencias disponibles, optaremos por el de 220Ω como el que utilizaremos en el ejercicio.


4. Ahora viene el código, como podemos ver, hemos colocado el led en el puerto 2. Por lo tanto le tenemos que decir al Arduino que el puerto 2 está ocupado por un Led. Esa información la colocaremos en el void setup(), que es donde se le indica al Arduino todas las configuraciones de nuestro sistema ensamblado:

```
void setup() {
pinMode(2, OUTPUT);

}
```

5. A continuación, pondremos las instrucciones que realizará nuestro arduino. Dichas instrucciones las colocamos en el void loop(). En este caso, le indicaremos que escriba en nuestro pin digital un valor alto (HIGH) durante un segundo, en pocas palabras, enciende el LED, para que finalmente lo apague (LOW) durante un segundo (delay):

```
void loop() {
digitalWrite(2, HIGH);
delay(1000);
digitalWrite(2, LOW);
delay(1000);
}
```

6. El código debe de quedarte así:

[]!(https://github.com/jmacalupur/helloLed/blob/master/04arduinoCode.png)

7. Ahora, sólo nos queda subir nuestro código y hacerlo funcionar. 

	7.1. Primero conectamos la placa Arduino a nuestra computadora con el cable USB-B. 

	7.2. En la ventana del IDE de arduino, aparece un botón de Salvar (Guardar como...), hacemos click ahí y lo guardamos en alguna parte de nuestro computador:

	[]!(https://github.com/jmacalupur/helloLed/blob/master/05arduinoSave.png)

	7.3. Recuerda que debes de asignar la placa Arduino UNO y el puerto al cual se encuentra conectado:

	[]!()
	[]!()

	7.4 Luego verifica que el código se encuentra bien:

	[]!(https://github.com/jmacalupur/helloLed/blob/master/06arduinoVerify.png)

	7.5 Finalmente, sube el código a la placa Arduino y ¡enjoy!

	[]!(https://github.com/jmacalupur/helloLed/blob/master/07arduinoSend.png)

	[]!(https://github.com/jmacalupur/helloLed/blob/master/08arduinoSendZoom.png)	
	Botón de enviar
	

Eso es todo. Ahora ya sabemos:

1. Funciones básicas del Arduino
2. Cómo podemos determinar la mejor resistencia para que nuestros sistema no se dañe.
3. Cómo concetar y formar un circuito con nuestra protoboard.
4. Las partes principales de la estructura de código del Arduino. 
5. Cómo subir el código hacia nuestra placa y que funcione correctamente.


 




