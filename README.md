# 🍎 Flutter iOS Testing — Without macOS / Sin macOS

---

## 🧪 Testing Flutter Apps on iOS — Without macOS

Normally, building an installable `.ipa` for iOS requires a Mac and an **Apple Developer Program** license. This tutorial covers alternatives using **simulators and virtual environments**, ideal when those requirements aren't available.

> **Note:** This assumes you already have a stable Flutter app in a GitHub repository.

---

### Available Methods

| # | Method | Difficulty | Physical Device? |
|---|--------|------------|-----------------|
| [1](#method-1-virtual-iphone-emulator) | Virtual iPhone (emulator) | 🟢 Easy | No |
| [2](#method-2-emulate-android-on-a-real-iphone) | Android emulated on real iPhone | 🟡 Medium | Yes (via browser) |
| [3](#method-3-install-a-real-ipa-on-iphone-temporary) | Real IPA on iPhone (temporary, 7 days) | 🔴 Hard | Yes |

---

### Method 1: Virtual iPhone (Emulator)

#### 1.1 — Create an Appetize.io account

1. Go to [https://appetize.io/](https://appetize.io/)
2. Click **Log In** → **Login with GitHub**
3. Sign in with your GitHub account

#### 1.2 — Build the app for simulator in Codemagic

1. Go to [https://codemagic.io/start/](https://codemagic.io/start/)
2. Click the **GitHub** logo and sign in

   ![GitHub login](https://github.com/user-attachments/assets/de84b586-2ebd-407d-a700-f74495b1c4be)

3. Select **Get Started**

   ![Get Started](https://github.com/user-attachments/assets/e1614a56-e15f-4697-8b89-751cee2e5092)

4. Choose **GitHub** and click **Authorize Codemagic**  
   _(Wait ~15 seconds, close the extra window, and reload)_
5. Re-authorize if prompted
6. Select your app's repository from the list

   ![Select repository](https://github.com/user-attachments/assets/ace189f9-02f1-4c38-99c6-37cbde37e743)

7. On the next screen, check **iOS** only

   ![Check iOS](https://github.com/user-attachments/assets/22c86532-11a4-4e1a-ab1f-1f3d2aeaf1d3)

8. Scroll to the **Build** section → under **Build arguments (iOS)**, enter: `--simulator`

   ![Build arguments](https://github.com/user-attachments/assets/c5512f78-915d-492b-ab72-b5d67fb3e60d)

9. Click **Save changes** (green button, top-right corner)

   ![Save changes](https://github.com/user-attachments/assets/fdc8e769-5754-4191-9005-32d2fd8c4ed8)

10. Click **Start your first build**

    ![Start first build](https://github.com/user-attachments/assets/91b09bda-096f-48ba-a1cb-e04535469fe9)

11. Click **Start new build** _(takes ~5 minutes)_

    ![Start new build](https://github.com/user-attachments/assets/bb3c1a2d-5a0d-402d-94b8-39df4fd91c74)

12. Once done, download the **`Runner.app.zip`** file

    ![Download Runner.app.zip](https://github.com/user-attachments/assets/fcd273ec-1d41-4255-83a9-b03dfd390cc1)

#### 1.3 — Upload the app to Appetize

1. Go to [https://appetize.io/apps](https://appetize.io/apps)
2. Click **Upload App**

   ![Upload App](https://github.com/user-attachments/assets/7219d46f-0ee8-41d0-8782-6bbb5dd110fa)

3. Click **Select A File** and select your **`Runner.app.zip`**

   ![Select A File](https://github.com/user-attachments/assets/7f011615-8e8f-458a-9044-176f5ad46307)

4. Click **Start** and configure the virtual device (use the recommended settings shown on screen)

   ![Configure device](https://github.com/user-attachments/assets/66f49c70-eae8-4d0a-ab63-bab40b6759c0)

5. Click **Tap to Start**

   ![Tap to Start](https://github.com/user-attachments/assets/50b1f935-942f-430c-a3b6-d595d9d7b2e0)

6. Your app will be running on a virtual iOS device!

   ![App running](https://github.com/user-attachments/assets/7d166192-6b8d-4e77-bb36-e454fcb93ef1)

---

### Method 2: Emulate Android on a Real iPhone

> **Requirement:** Your app must be compiled as an `.apk`.  
> Not sure how? → [See: Build APK](#-build-apk)

1. Go to [https://appetize.io/apps/](https://appetize.io/apps/)
2. Click **Upload App**

   ![Upload App](https://github.com/user-attachments/assets/07aa6b26-bebd-4280-89d0-d982c0650bf4)

3. Click **Select A File** → select your **APK**

   ![Select APK](https://github.com/user-attachments/assets/785f3c90-10fc-4280-8214-68a709752cad)

4. Click **Share App**

   ![Share App](https://github.com/user-attachments/assets/7d1c4296-2275-4726-8faf-51d2ee0386c7)

5. Copy the **Embed URL** using the icon

   ![Embed URL](https://github.com/user-attachments/assets/dafba4eb-a604-440a-a7aa-f9191524f699)

6. Send that link to your iPhone (via WhatsApp or any other method)
7. On the iPhone, install **Fullmode: Minimal Browser** from the App Store
8. Enter the Embed URL when prompted (adjust zoom to fill the screen)
9. Tap **Tap to Start** — your Android app will run on your iPhone

   ![Result](https://github.com/user-attachments/assets/03d584a1-746c-4825-8081-379617e5ffd8)

---

### Method 3: Install a Real IPA on iPhone (Temporary)

> ⚠️ **NOT RECOMMENDED if you only have Windows.**  
> The installation **expires after 7 days** and requires Linux (Fedora/RPM).

#### 3.1 — Build in Codemagic

1. Go to [https://codemagic.io/start/](https://codemagic.io/start/)
2. Click the **GitHub** logo and sign in

   ![GitHub login](https://github.com/user-attachments/assets/de84b586-2ebd-407d-a700-f74495b1c4be)

3. Select **Get Started**

   ![Get Started](https://github.com/user-attachments/assets/e1614a56-e15f-4697-8b89-751cee2e5092)

4. Choose **GitHub** and click **Authorize Codemagic**  
   _(Wait ~15 seconds, close the extra window, and reload)_
5. Re-authorize if prompted
6. Select your app's repository from the list

   ![Select repository](https://github.com/user-attachments/assets/ace189f9-02f1-4c38-99c6-37cbde37e743)

7. On the next screen, check **iOS** only

   ![Check iOS](https://github.com/user-attachments/assets/22c86532-11a4-4e1a-ab1f-1f3d2aeaf1d3)

8. Scroll to the **Build** section → under **Mode**, set it to **Release**

   ![Save changes](https://github.com/user-attachments/assets/fdc8e769-5754-4191-9005-32d2fd8c4ed8)

9. Click **Save changes** (green button, top-right corner)

10. Click **Start your first build**

    ![Start first build](https://github.com/user-attachments/assets/91b09bda-096f-48ba-a1cb-e04535469fe9)

11. Click **Start new build** _(takes ~5 minutes)_

    ![Start new build](https://github.com/user-attachments/assets/bb3c1a2d-5a0d-402d-94b8-39df4fd91c74)

12. Once done, download the **`Runner.app.zip`** file

    ![Download Runner.app.zip](https://github.com/user-attachments/assets/fcd273ec-1d41-4255-83a9-b03dfd390cc1)

#### 3.2 — Convert `.app.zip` to `.ipa`

1. Download the conversion script: **[convert_appzip_to_ipa.bat](https://github.com/AngelDev2343/AppZip-To-IPA/releases/download/v1.0/convert_appzip_to_ipa.bat)**
2. Open a terminal and run:
   ```bash
   cd %USERPROFILE%\Downloads
   convert_appzip_to_ipa.bat Runner.app.zip
   ```

#### 3.3 — Install the IPA on the iPhone

You'll need a computer or VM running **Fedora Linux** (or a DNF/RPM-compatible distro).  
Follow the detailed instructions here: **[Install IPA](https://github.com/AngelSPerez/ipa/blob/main/README.md)**

> **Note:** This step is done from the Linux terminal.

---

### 📦 Build APK

1. Open your favorite IDE (VS Code, Android Studio, etc.)
2. Open your Flutter project folder
3. Open a terminal and run:
   ```bash
   flutter doctor
   ```
4. Make sure **Android Toolchain** shows ✅ OK
5. Build the APK:
   ```bash
   flutter build apk --debug
   ```
   _(Takes ~15 minutes. The terminal will show the output file path when done)_





---

## 🧪 Probar apps de Flutter en iOS — Sin macOS

Normalmente, crear un `.ipa` instalable para iOS requiere una Mac y una licencia del **Apple Developer Program**. Este tutorial cubre alternativas usando **simuladores y entornos virtuales**, ideales cuando no se cuenta con esos requisitos.

> **Nota:** Se asume que ya tienes una app Flutter estable en un repositorio de GitHub.

---

### Métodos disponibles

| # | Método | Dificultad | ¿Dispositivo físico? |
|---|--------|------------|----------------------|
| [1](#método-1-iphone-virtual-emulador) | iPhone virtual (emulador) | 🟢 Fácil | No |
| [2](#método-2-emular-android-en-iphone-real) | Android emulado en iPhone real | 🟡 Medio | Sí (vía browser) |
| [3](#método-3-instalar-ipa-real-en-iphone-temporal) | IPA real en iPhone (temporal, 7 días) | 🔴 Difícil | Sí |

---

### Método 1: iPhone virtual (Emulador)

#### 1.1 — Crear cuenta en Appetize.io

1. Ve a [https://appetize.io/](https://appetize.io/)
2. Clic en **Log In** → **Login with GitHub**
3. Inicia sesión con tu cuenta de GitHub

#### 1.2 — Compilar la app para simulador en Codemagic

1. Ve a [https://codemagic.io/start/](https://codemagic.io/start/)
2. Clic en el logo de **GitHub** e inicia sesión

   ![GitHub login](https://github.com/user-attachments/assets/de84b586-2ebd-407d-a700-f74495b1c4be)

3. Selecciona **Get Started**

   ![Get Started](https://github.com/user-attachments/assets/e1614a56-e15f-4697-8b89-751cee2e5092)

4. Elige **GitHub** y clic en **Authorize Codemagic**  
   _(Espera ~15 segundos, cierra la ventana extra y recarga)_
5. Autoriza nuevamente si se solicita
6. Selecciona el repositorio de tu app en la lista

   ![Seleccionar repositorio](https://github.com/user-attachments/assets/ace189f9-02f1-4c38-99c6-37cbde37e743)

7. En la siguiente pantalla, marca únicamente **iOS**

   ![Marcar iOS](https://github.com/user-attachments/assets/22c86532-11a4-4e1a-ab1f-1f3d2aeaf1d3)

8. Desplázate a la sección **Build** → en **Build arguments (iOS)** escribe: `--simulator`

   ![Build arguments](https://github.com/user-attachments/assets/c5512f78-915d-492b-ab72-b5d67fb3e60d)

9. Clic en **Save changes** (botón verde, esquina superior derecha)

   ![Save changes](https://github.com/user-attachments/assets/fdc8e769-5754-4191-9005-32d2fd8c4ed8)

10. Clic en **Start your first build**

    ![Start first build](https://github.com/user-attachments/assets/91b09bda-096f-48ba-a1cb-e04535469fe9)

11. Clic en **Start new build** _(tarda ~5 minutos)_

    ![Start new build](https://github.com/user-attachments/assets/bb3c1a2d-5a0d-402d-94b8-39df4fd91c74)

12. Al finalizar, descarga el archivo **`Runner.app.zip`**

    ![Descargar Runner.app.zip](https://github.com/user-attachments/assets/fcd273ec-1d41-4255-83a9-b03dfd390cc1)

#### 1.3 — Cargar la app en Appetize

1. Ve a [https://appetize.io/apps](https://appetize.io/apps)
2. Clic en **Upload App**

   ![Upload App](https://github.com/user-attachments/assets/7219d46f-0ee8-41d0-8782-6bbb5dd110fa)

3. Clic en **Select A File** y selecciona tu **`Runner.app.zip`**

   ![Select A File](https://github.com/user-attachments/assets/7f011615-8e8f-458a-9044-176f5ad46307)

4. Clic en **Start** y configura el dispositivo virtual (usa los valores recomendados en pantalla)

   ![Configurar dispositivo](https://github.com/user-attachments/assets/66f49c70-eae8-4d0a-ab63-bab40b6759c0)

5. Clic en **Tap to Start**

   ![Tap to Start](https://github.com/user-attachments/assets/50b1f935-942f-430c-a3b6-d595d9d7b2e0)

6. ¡Tu app estará corriendo en iOS virtual!

   ![App corriendo](https://github.com/user-attachments/assets/7d166192-6b8d-4e77-bb36-e454fcb93ef1)

---

### Método 2: Emular Android en iPhone real

> **Requisito:** Tener la app compilada como `.apk`.  
> ¿No sabes cómo? → [Ver sección: Compilar APK](#-compilar-apk)

1. Ve a [https://appetize.io/apps/](https://appetize.io/apps/)
2. Clic en **Upload App**

   ![Upload App](https://github.com/user-attachments/assets/07aa6b26-bebd-4280-89d0-d982c0650bf4)

3. Clic en **Select A File** → selecciona tu **APK**

   ![Select APK](https://github.com/user-attachments/assets/785f3c90-10fc-4280-8214-68a709752cad)

4. Clic en **Share App**

   ![Share App](https://github.com/user-attachments/assets/7d1c4296-2275-4726-8faf-51d2ee0386c7)

5. Copia el **Embed URL** con el ícono

   ![Embed URL](https://github.com/user-attachments/assets/dafba4eb-a604-440a-a7aa-f9191524f699)

6. Envía ese link a tu iPhone (por WhatsApp u otro medio)
7. En el iPhone, instala **Fullmode: Minimal Browser** desde la App Store
8. Ingresa el Embed URL cuando la app lo solicite (ajusta el zoom para pantalla completa)
9. Tap en **Tap to Start** — la app Android correrá en tu iPhone

   ![Resultado](https://github.com/user-attachments/assets/03d584a1-746c-4825-8081-379617e5ffd8)

---

### Método 3: Instalar IPA real en iPhone (temporal)

> ⚠️ **NO RECOMENDADO si solo tienes Windows.**  
> La instalación expira en **7 días** y requiere Linux (Fedora/RPM).

#### 3.1 — Compilar en Codemagic

1. Ve a [https://codemagic.io/start/](https://codemagic.io/start/)
2. Clic en el logo de **GitHub** e inicia sesión

   ![GitHub login](https://github.com/user-attachments/assets/de84b586-2ebd-407d-a700-f74495b1c4be)

3. Selecciona **Get Started**

   ![Get Started](https://github.com/user-attachments/assets/e1614a56-e15f-4697-8b89-751cee2e5092)

4. Elige **GitHub** y clic en **Authorize Codemagic**  
   _(Espera ~15 segundos, cierra la ventana extra y recarga)_
5. Autoriza nuevamente si se solicita
6. Selecciona el repositorio de tu app en la lista

   ![Seleccionar repositorio](https://github.com/user-attachments/assets/ace189f9-02f1-4c38-99c6-37cbde37e743)

7. En la siguiente pantalla, marca únicamente **iOS**

   ![Marcar iOS](https://github.com/user-attachments/assets/22c86532-11a4-4e1a-ab1f-1f3d2aeaf1d3)

8. Desplázate a la sección **Build** → en **Mode**, selecciona **Release**

   ![Save changes](https://github.com/user-attachments/assets/fdc8e769-5754-4191-9005-32d2fd8c4ed8)

9. Clic en **Save changes** (botón verde, esquina superior derecha)

10. Clic en **Start your first build**

    ![Start first build](https://github.com/user-attachments/assets/91b09bda-096f-48ba-a1cb-e04535469fe9)

11. Clic en **Start new build** _(tarda ~5 minutos)_

    ![Start new build](https://github.com/user-attachments/assets/bb3c1a2d-5a0d-402d-94b8-39df4fd91c74)

12. Al finalizar, descarga el archivo **`Runner.app.zip`**

    ![Descargar Runner.app.zip](https://github.com/user-attachments/assets/fcd273ec-1d41-4255-83a9-b03dfd390cc1)

#### 3.2 — Convertir `.app.zip` a `.ipa`

1. Descarga el script de conversión: **[convert_appzip_to_ipa.bat](https://github.com/AngelDev2343/AppZip-To-IPA/releases/download/v1.0/convert_appzip_to_ipa.bat)**
2. Abre una terminal y ejecuta:
   ```bash
   cd %USERPROFILE%\Downloads
   convert_appzip_to_ipa.bat Runner.app.zip
   ```

#### 3.3 — Instalar el IPA en el iPhone

Necesitas una computadora o VM con **Fedora Linux** (o distro compatible con DNF/RPM).  
Sigue las instrucciones detalladas aquí: **[Instalar IPA](https://github.com/AngelSPerez/ipa/blob/main/README.md)**

> **Nota:** Este proceso se realiza desde la terminal de Linux.

---

### 📦 Compilar APK

1. Abre tu IDE favorito (VS Code, Android Studio, etc.)
2. Abre la carpeta de tu proyecto Flutter
3. Abre una terminal y ejecuta:
   ```bash
   flutter doctor
   ```
4. Verifica que **Android Toolchain** aparezca como ✅ OK
5. Compila el APK:
   ```bash
   flutter build apk --debug
   ```
   _(Tarda ~15 minutos. Al finalizar, la terminal mostrará la ruta del archivo generado)_
