# Task Manager App

---

## 🧑‍💻 Integrantes del Equipo
- Lara V. Cordero Rodríguez - R00607366 - lcordero7366@arecibointer.edu
- Dairan S. De Jesús Mora - R00611095 - ddejesus1095@arecibointer.edu
- Ian P. Padua Cuevas -R00608377 - ipadua8377@arecibointer.edu

---

## 🎯 Descripción General
Describe brevemente tu aplicación:
- ¿Qué hace?
  El Task Manager App es una app que gestiona tareas que le provee el usuario. Donde puede crear, tachar las tareas hechas y eliminar las tareas realizadas.
- ¿A quién va dirigida?
  Esta aplición esta dirigida a usuarios como estudiantes, profesionales o personas que desean gestionar de una manera organizada y flexible.
- ¿Qué problema resuelve o qué funcionalidad ofrece?
  La aplicación está diseñada para enfrentar los desafíos relacionados con la falta de organización y el control ineficaz de tareas. Ofrece una forma clara y ordenada de gestionar actividades, optimizando el flujo de trabajo y facilitando el cumplimiento de responsabilidades diarias. 
---

## ☁️ Servicios de Azure Utilizados

| Servicio              | Propósito dentro del proyecto                                             | Gratuito en Azure for Students |
| --------------------- | ------------------------------------------------------------------------- | ------------------------------ |
| Azure App Service     | Hospedaje de la aplicación web y gestión del entorno de ejecución         | ✅ Sí                           |
| Azure SQL Database    | Almacenamiento estructurado de los datos utilizados por la app            | ✅ Sí                           |
| Azure SQL Server      | Motor de base de datos para gestionar conexiones y seguridad              | ✅ Sí                           |


--- 

## 🧱 Diagrama de Arquitectura

![Diagrama](./imgs/diagrama_infraestructura_azure.png)

---

## ⚙️ Despliegue y Configuración

### 1. Preparación Local
1. Clonar el repositorio de github: https://github.com/javierdastas/comp4260
2. Configurar el entorno virtual en la terminal de Visual Studio Code `python -m venv venv`.
3. Al activar el entorno, instalas las dependencias con `pip install -r requirements.txt`.
4. Luego, configuras las variables de entorno en un `.env`
5. En la terminal de VSC se ejecuta en la terminal el comando de `python app.py`.

![Terminal_app.py](./imgs/python_app.py.png)

6. Al ejecutarse ese comando podras ver las configuraciones del "Host" y entras al puerto `http://127.0.0.1:5000`

7. Finalmente, se muestra la interfaz del Task Manager App y se nota la ruta en el browser, indicando la utilización del puerto correcto.

![Task_Maneger_Interfaz](./imgs/Interfaz_Task_Manager.png)


información Configuración en Azure Readme: 



### 🚀 2. Configuración en Azure ☁️

Este documento detalla los pasos realizados en el Azure Portal para la configuración de la aplicación web 🌐 y su conexión crucial con la base de datos Azure SQL 💾.

### 🛠️ Pasos Realizados en Azure Portal 🛠️

#### ⚙️ Configuración del App Service ⚙️

Se creó un **Web App** con los siguientes detalles clave:

* **🏷️ Nombre del Web App:** `app-tasks-ds`
* **🌍 Región:** East US
* **📂 Grupo de recursos:** `Proyecto_Final`
* **🔗 Dominio predeterminado:** `app-tasks-ds-aqgsaddfhneyhce6.eastus-01.azurewebsites.net`
* **⚙️ Plan de App Service:** `ASP-ServidorEstudiante1group-ad3c` (F1: 1)
*  **🔗 Repositorio conectado:** [https://github.com/DairaDoo/azure_students_project](https://github.com/DairaDoo/azure_students_project)

Este **Web App** servirá como la plataforma de ejecución para nuestra aplicación **Flask**.

#### 🔑 Variables de entorno definidas 🔑

Se definieron las siguientes **variables de entorno** dentro de la configuración del **App Service** para la conexión a la base de datos:

* `SQL_SERVER`
* `SQL_DATABASE`
* `SQL_USERNAME`
* `SQL_PASSWORD`

Estas variables serán utilizadas por la aplicación **Flask** para establecer una conexión segura con la base de datos **Azure SQL**.

#### 💾 Configuración del SQL Server 💾

Para la **persistencia de datos** de la aplicación, se configuró una base de datos **Azure SQL** siguiendo estos pasos esenciales:

1.  ✨ Se creó una **Azure SQL Database** con el nombre: `proyecto_estudiante`.
2.  📂 Se seleccionó o creó un **Grupo de recursos** denominado: `DefaultResourceGroup-EUS`.
3.  🌐 Se provisionó un nuevo **servidor** llamado: `proyecto-final-cloud`, ubicado en la región: `West US 2`.
4.  🛡️ Se configuró la **autenticación** del servidor mediante **Microsoft Entra ID** y una cuenta de administrador de SQL, con los siguientes detalles:
    * **👤 Nombre de administrador:** `lcordero123`
    * **🏢 Microsoft Entra ID:** `lcordero7366@arecibointer.edu`
    * **🔒 Contraseña:** (Contraseña personalizada establecida durante la creación).
5.  🚦 Se agregaron las **direcciones IPv4** necesarias a la configuración del **firewall** del servidor para permitir el acceso.
6.  ✅ Finalmente, se creó la base de datos `proyecto_estudiante` en el servidor `proyecto-final-cloud`, completando la configuración de la base de datos para nuestro proyecto.

#### 🔗 Conexión del App Service a la Base de Datos 🔗

Una vez que la base de datos estuvo operativa, se obtuvo la **cadena de conexión (connection string)** 🔑. Esta cadena se utilizó para configurar las **variables de entorno** (`SQL_SERVER`, `SQL_DATABASE`, `SQL_USERNAME`, `SQL_PASSWORD`) dentro de la configuración del **App Service**. Al establecer estas variables con los detalles de conexión correctos, la aplicación **Flask** desplegada en el **Web App** pudo establecer comunicación y realizar operaciones en la base de datos `proyecto_estudiante`.


### 3. Automatización (opcional)
Si usaste GitHub Actions, Terraform, Bicep, ARM Templates, etc., explica:
- Qué automatiza
- Dónde está el archivo (.yml, .json, etc.)

---

## 💻 Enlace a la Aplicación Desplegada
> [https://tu-app.azurewebsites.net](https://tu-app.azurewebsites.net)

---

## 💸 Estimación del Costo (Azure Pricing Calculator)
Describe el costo estimado mensual de tu arquitectura si se ejecutara sin los beneficios gratuitos.  
Incluye una captura de pantalla o PDF del cálculo.  
> [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)

---

## 📁 Capturas del Portal de Azure
Agrega capturas mostrando:
- Los recursos creados (App Service, SQL Database, Storage, etc.)
- Configuraciones clave
- Diagnóstico o panel de monitoreo (opcional)

---

## 📘 Lecciones Aprendidas
- ¿Qué retos enfrentaron y cómo los resolvieron? Tuvimos dos principales retos. El primero fue conectar con la base de datos     desde Azure App Service, lo cual resolvimos al identificar que el problema estaba en el driver: necesitábamos la versión 18 en lugar de la 17. El segundo fue ejecutar el proyecto localmente, donde las variables del archivo .env no se cargaban correctamente. Esto se solucionó integrando la librería dotenv, que permitió acceder a las variables de entorno y establecer la conexión exitosamente.

- ¿Qué aprendieron sobre trabajar con servicios cloud? Aprendimos que los servicios en la nube ofrecen una alta escalabilidad y flexibilidad, lo que facilita mucho el proceso de despliegue de aplicaciones. Además, notamos que al trabajar en equipo de forma distribuida, la nube permite una integración más eficiente entre las distintas partes del proyecto, brindando una mayor confiabilidad, seguridad y simplicidad en la implementación grupal de un proyecto.

- ¿Qué mejorarían en una próxima versión del proyecto? En una próxima versión del proyecto, nos gustaría implementar una arquitectura más escalable y robusta, incorporando el uso de roles, medidas de seguridad más avanzadas y la integración entre distintos servicios en la nube. Esto nos permitiría comprender mejor cómo se relacionan los componentes dentro de Azure y cómo diseñar soluciones más completas y seguras en un entorno real.

---

## 📚 Repositorio del Código
Enlace:
> [https://github.com/DairaDoo/azure_students_project](https://github.com/DairaDoo/azure_students_project)

---

## 📄 Instrucciones para Reproducir el Proyecto
1. Clonar el repositorio.
2. Instalar dependencias: `pip install -r requirements.txt` (si aplica).
3. Crear base de datos (opcional: script SQL incluido).
4. Crear variables de entorno necesarias.
5. Ejecutar la aplicación: `python app.py` o comando correspondiente.
6. Acceder desde `localhost` o mediante el App Service.

---

## ✅ Checklist Final
- [ ] App funcional y desplegada
- [ ] Servicios gratuitos utilizados correctamente
- [ ] Diagrama de arquitectura incluido
- [ ] Documentación clara y completa
- [ ] Costos estimados incluidos
- [ ] Repositorio disponible en GitHub
- [ ] Lecciones aprendidas y reflexión final escritas

---

## 🎓 Créditos
Curso: Cloud Computing  
Profesor: Javier A. Dastas  
Universidad Interamericana de Puerto Rico – Recinto de Arecibo