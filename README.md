# Cómo probar apps de Flutter en iOS fácil

Primero hay que aclarar algo importante: para crear aplicaciones instalables para iOS
( **.ipa** ) normalmente se necesita una computadora con macOS y, en muchos casos,
una licencia oficial del **Apple Developer Program** .


Por eso, en este tutorial veremos algunas alternativas y métodos para realizar pruebas
y desarrollo básico sin contar con esos requisitos. Sin embargo, estas opciones están
enfocadas principalmente en **simuladores y entornos virtuales**, por lo que no
permitirán instalar la aplicación de forma real y nativa en un dispositivo físico con iOS.


**Nota:** este tutorial asume que ya cuentas con una aplicación desarrollada y
relativamente estable lista para realizar pruebas (tiene que estar en un repositorio de
GitHub).

## Método 1: instalar en iPhone virtual

#### ●​ Crear cuenta en emulador múltiple


1.​ [Dirígite a la siguiente dirección web: https://appetize.io/](https://appetize.io/)
2.​ Selecciona el botón “Log In”.
3.​ Seguido de eso, selecciona “Login with GitHub”
4.​ Inicia sesión con tu GitHub.
#### ●​ Crear cuenta en entorno de desarrollo (Codemagic)

●​ [Ahora, dirígete a esta dirección web: https://codemagic.io/start/](https://codemagic.io/start/)
●​ Da clic al logo de Github a continuación.


●​ Inicia sesión y autoriza.
●​ Selecciona el botón “Get Started”.


●​ Ahora selecciona “GitHub”.
●​ Da clic en “Authorize Codemagic”, después de 15 segundos (y ya
autorizado) cierra la ventana extra y recarga la ventana actual.
●​ Vuelve a seleccionar “GitHub” y vuelve a autorizar.


●​ En la lista de repositorios selecciona el de tu aplicación:


●​ En la siguiente pantalla marca solamente “ **iOS** ”.


●​ Desliza hacia abajo hasta encontrar el apartado “ **Build** ” y da clic sobre el.
●​ Y en la sección de “ **Build arguments** ”, colocarán “ **--simulator** ” en el
apartado para “ **iOS** ”.


●​ Justo después de esto damos clic en el botón verde de la esquina
superior derecha que dice “ **Save changes** ”.


●​ Luego en “ **Start your first build** ”.​


●​ Y después en el botón “ **Start new build** ” (el empaquetado suele tardar
alrededor de 5 minutos).​


●​ Después darás clic en el archivo “Runner.app.zip” para descargarlo.


​

### ●​ Cargar app en iOS (Emulador)


●​ [Ingresamos a la página Appetize Apps.](https://appetize.io/apps)
●​ Daremos clic en el botón “ **Upload App** ”.​


●​ Luego en el botón “ **Select A File** ”.​


●​ Después seleccionamos nuestra app (“ **Runner.app.zip** ”)
●​ Luego le damos clic en “ **Start** ”


●​ Y en la siguiente pantalla colocaremos los datos del dispositivo virtual, los
recomendados son los que se ven a continuación.


●​ Cuando ya hayas colocado los datos del dispositivo darás clic en el botón
“ **Tap to Start** ”.​


​
​
​


●​ Y listo, ya estaría ejecutándose tu aplicación en un entorno virtual de iOS
(en mi caso una calculadora básica).


## Método 2: emular Android en iPhone real

**Nota:** para este método necesitarás tener tu app ya compilada en formato **.apk**, si no
es así, dirígete a esta sección: ¿Cómo compilar apk?

#### ●​ Emulador múltiple


●​ Dirígite a la siguiente dirección web: [https://appetize.io/apps/](https://appetize.io/apps/)
●​ Si no tienes cuenta crea una, las instrucciones están **aquí** .
●​ Una vez aquí, selecciona el botón “ **Upload App** ”.​


.
●​ Luego, da clic en el botón “ **Select A File** ” y selecciona tu **APK** .​


●​ Después da clic en el botón de “ **Share App** ”.


●​ Luego, copiamos el link “ **Embed URL** ” con el icono.


●​ Después pasa ese mismo link a tu iPhone (puedes usar WhatsApp).
●​ Luego en tu iPhone instalaras la app llamada “ **Fullmode: Minimal**
**Browser** ”, disponible en la AppStore.
●​ Cuando te pida una URL colocaras la que anteriormente mandaste a tu
iPhone (Ajusta el zoom para que ocupe toda la pantalla).


●​ Luego das clic en “Tap to Start” y listo ya estaría funcionando en tu
iPhone.​


Resultado:​


## Método 3: instalar app realmente en iPhone de manera temporal (significativamente más difícil y con fecha de expiración en 7 días)

**NO RECOMENDADO SI SOLO TIENES WINDOWS**

#### ●​ Crear cuenta en entorno de desarrollo (Codemagic)

●​ [Dirígete a esta dirección web: https://codemagic.io/start/](https://codemagic.io/start/)
●​ Da clic al logo de Github a continuación.


●​ Inicia sesión y autoriza.
●​ Selecciona el botón “Get Started”.


●​ Ahora selecciona “GitHub”.
●​ Da clic en “Authorize Codemagic”, después de 15 segundos (y ya
autorizado) cierra la ventana extra y recarga la ventana actual.
●​ Vuelve a seleccionar “GitHub” y vuelve a autorizar.
●​ En la lista de repositorios selecciona el de tu aplicación:


●​ En la siguiente pantalla marca solamente “ **iOS** ”.


●​ Desliza hacia abajo hasta encontrar el apartado “ **Build** ” y da clic sobre el.
●​ Y en la sección de “ **Mode** ”, colocarán “ **Release** ”.
●​ Justo después de esto damos clic en el botón verde de la esquina
superior derecha que dice “ **Save changes** ”.


●​ Luego en “ **Start your first build** ”.​


●​ Y después en el botón “ **Start new build** ” (el empaquetado suele tardar
alrededor de 5 minutos).​


●​ Después darás clic en el archivo “Runner.app.zip” para descargarlo.


●​ Ahora tenemos que convertir este archivo descargado a “ **.ipa** ” por lo cual
descargaremos el siguiente script **[DESCARGAR](https://github.com/AngelDev2343/AppZip-To-IPA/releases/download/v1.0/convert_appzip_to_ipa.bat)** .
●​ Después abrimos una nueva terminal y ejecutaremos el siguiente
comando “ **cd %USERPROFILE%\Downloads** ”
●​ Justo después de ese comando ejecutamos el siguiente
“ **convert_appzip_to_ipa.bat Runner.app.zip** ”.
●​ Cuando tengas tu “ **Runner.ipa** ” necesitarás una computadora o VM con
**Fedora Linux** (lamentablemente en Windows es extremadamente dificil


casi imposible) o una distribución compatible con **DNF/RPM**, ahora sigue
las instrucciones detalladas en el siguiente link: **[Instalar IPA](https://github.com/AngelSPerez/ipa/blob/main/README.md)**


**Nota:** Esto se hace desde la terminal de Linux


# ¿Cómo compilar APK?

●​ Abre tu IDE favorito (Ej. VS Code o Antigravity).
●​ Ahora, abre la carpeta de tu proyecto Flutter.
●​ Seguido abre una nueva terminal.
●​ En esta terminal, ejecuta el comando: flutter doctor
●​ Asegúrate de que esté OK la “Android Toolchain”.


●​ Si todo está bien, ejecuta el siguiente comando (este compila la apk, tarda
aproximadamente 15 minutos): flutter build apk --debug
●​ Cuando termine te dará la ruta, con esto ya tendrás tu archivo APK y lo podrás
mover a donde quieras.​


