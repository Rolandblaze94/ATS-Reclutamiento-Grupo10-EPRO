# ATS-Reclutamiento-Grupo10-EPRO
Proyecto EPRO - Sistema de Reclutamiento (ATS) - Grupo 10

Orientado a la gestión y centralización del proceso de selección de personal para el área de Recursos Humanos. Desarrollado como una aplicación web Java bajo la arquitectura Jakarta EE 10.

## 🛠️ Tecnologías y Requisitos del Sistema

El proyecto está estructurado como una aplicación web Java empaquetada en formato `war` administrada con Maven.


| **Sistema Operativo**: Windows 10/11 o equivalente - Ambiente local de desarrollo y pruebas 
| **Java** : JDK 11 o superior - Compilación y ejecución (definida en `pom.xml`) 
| **Servidor Web** : Apache Tomcat 10.x - Ejecución de JSP y Servlets Jakarta 
| **Base de Datos**: MySQL Server 8.x - Persistencia de usuarios, vacantes, candidatos y evaluaciones 
| **IDE Recomendado**: Apache NetBeans o compatible - Apertura, compilación y ejecución del proyecto 
| **Gestor BD**: MySQL Workbench o phpMyAdmin - Creación de la base de datos y verificación de tablas 
| **Dependencias**: Maven - Administración de Jakarta EE, JSTL, MySQL Connector y EclipseLink 

### 📦 Principales Dependencias (`pom.xml`)
```xml
<packaging>war</packaging>
<!-- Dependencias Core -->
<dependency>jakarta.jakartaee-api</dependency> <!-- Versión 10.0.0 -->
<dependency>jakarta.servlet.jsp.jstl</dependency>
<dependency>com.mysql:mysql-connector-j</dependency>
<dependency>org.eclipse.persistence:org.eclipse.persistence.jpa</dependency>
```
## 📊 Alcance del Proyecto y Requerimientos

### Matriz de Requerimientos Funcionales (RF)
*   **RF-01 Crear vacantes** ➔  Cumplido
*   **RF-02 Editar y cerrar vacantes** ➔  Cumplido
*   **RF-03 Registrar candidatos** ➔  Cumplido
*   **RF-04 Adjuntar CV en PDF** ➔  Cumplido
*   **RF-05 Pipeline de candidatos** ➔ 🟡 Implementación parcial
*   **RF-06 Registrar evaluaciones** ➔ 🟡 Implementación parcial
*   **RF-07 Registrar comentarios cualitativos** ➔ 🟡 Implementación parcial
*   **RF-10 Autenticación de usuarios** ➔  Cumplido
*   **RF-11 Roles de usuario** ➔ 🟡 Cumplido parcialmente

### 🎯 Funcionalidades Alcanzadas
*   Administración completa de vacantes (Creación, modificación y eliminación).
*   Registro, almacenamiento de candidatos y carga de documentos PDF (vía URL de Google Drive).
*   Gestión de usuarios con roles de RRHH y Entrevistador junto al control de sesiones seguro.
*   Gestión básica del pipeline de selección y registro de evaluaciones con puntajes.
*   Diseño responsive adaptado a dispositivos móviles.

### ⏳ Funcionalidades Pendientes (Próximas Versiones)
*   **RF-08 / RF-09:** Reportes de candidatos por estado y tiempo promedio de contratación.
*   Validación estricta de permisos por rol en la totalidad de los módulos.
*   Optimización en las validaciones de archivos y formularios del sistema.
*   Incremento de accesibilidad y usabilidad general en la interfaz.

## 🧪 Pruebas y Control de Calidad

*   **Casos de prueba definidos:** 15
*   **Casos ejecutados formalmente:** 8 (con evidencias técnicas)
*   **Resultados:** 7 exitosos (**PASS**) | 1 fallido (**FAIL**)
*   **Cobertura de requerimientos críticos:** 66.7%

> ⚠️ **Nota de mejora:** El caso fallido está asociado directamente a la *validación de acceso por roles*, el cual queda registrado en el log de defectos para corregirse prioritariamente en la siguiente iteración.

## 🗂️ Evidencias del Proyecto

### 💻 Evidencias Técnicas y de Diseño
*   **Estructura de Código:** Organizado formalmente por capas (Presentación, Lógica de Negocio y Datos).
*   **Control de Versiones:** Repositorio en GitHub con historial de commits y pull requests estructurados.
*   **Base de Datos:** Modelo entidad-relación normalizado en MySQL.
*   **Modelado UML:** Diagramas de casos de uso, diagramas de clases y diagramas de secuencia.
*   **Prototipado:** Diseños de interfaces funcionales para el sistema.

### 📄 Evidencias Documentales Disponibles
*   Documento de levantamiento de requerimientos y entrevistas a Recursos Humanos.
*   Diagnóstico de procesos AS-IS y propuesta de mejora TO-BE.
*   Plan de pruebas, Registro de defectos y Checklist de usabilidad.
*   Manual de usuario y Manual Técnico.

## 📖 Manual de Operación (Guía de Uso Rápido)

### 1. Registro e Inicio de Sesión
1. Dirígete a la página principal del sistema y haz clic en **Registrarse**.
2. Introduce un nombre de usuario, contraseña y asigna el **Rol** correspondiente.
3. Al hacer clic en **Crear cuenta**, se validará el registro con un mensaje de éxito.
4. Regresa a la pantalla principal, introduce tus credenciales y presiona **Entrar al sistema**.

### 2. Publicar una Vacante
1. En el menú superior de la pantalla de inicio, selecciona **Publicar Trabajo**.
2. Presiona el botón **Nueva Vacante**.
3. Rellena los campos: *Nombre del puesto, Área/Departamento, Salario, Estado* y añade una *Descripción*.
4. Haz clic en **Crear Vacante** para verla publicada inmediatamente en la lista del inicio.

### 3. Aplicar a una Vacante (Candidatos)
1. Desde la pantalla de inicio, haz clic en el botón **Aplicar** de la vacante de interés.
2. Completa el formulario con tu *Nombre completo, Correo electrónico* y el *Enlace (URL) a tu CV en Google Drive*.
3. Presiona **Enviar postulación** y el sistema confirmará la recepción mediante un modal emergente.

### 4. Evaluar un Candidato
1. Navega a la sección de **Candidatos** desde el menú principal.
2. Selecciona al postulante de la lista.
3. Asigna el *Entrevistador* responsable, el *Puntaje de evaluación* y redacta los *Comentarios cualitativos*.
4. Guarda la información para actualizar de forma inmediata la tabla de evaluaciones del pipeline.
