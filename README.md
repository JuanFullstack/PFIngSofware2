## Proyecto Final - Ingeniería de Sofware II 
# Estrategias de Ramificación - Modelo GitFlow

### **Integrantes del Grupo:**
* **Cano Arce**, Valentina
* **Cano**, Juan
* **Gonzalez**, Santiago
* **Lobo**, Sergio

---



## 1. Introducción a SCM

La Gestión de la Configuración de Software (SCM) es una disciplina transversal en la ingeniería de software que administra la evolución de productos complejos. Debido a que el software es un activo intangible y en constante cambio, la SCM actúa como el marco que organiza y controla cada modificación. Su importancia fundamental reside en que permite la colaboración de múltiples integrantes sin comprometer la integridad del sistema, asegurando que siempre exista una línea base (baseline) estable y recuperable ante cualquier error en el desarrollo.

En el contexto actual, donde los ciclos de entrega son cada vez más cortos, el uso de Sistemas de Control de Versiones (VCS) como Git se ha consolidado como el estándar de la industria para gestionar esta mutabilidad. Para organizar el trabajo en equipo, referentes del área como Vincent Driessen han formalizado modelos de ramificación (branching) profesionales. En este trabajo, aplicamos específicamente el modelo **GitFlow**, el cual permite gestionar la complejidad del desarrollo paralelo y los lanzamientos de versiones mediante una estructura de ramas que asegura la trazabilidad total del proyecto.

## 2. Desarrollo práctico

En esta sección se describe la metodología aplicada para la construcción colaborativa de este informe, utilizando Git como tecnología de control de versiones distribuido. El objetivo es proporcionar una guía reproducible del flujo de trabajo GitFlow.

  ###  2.1 Marco Teórico y Conceptos Fundamentales 
 Para comprender la implementación práctica, es necesario definir los pilares de la Gestión de la Configuración de Software (SCM) aplicados en este proyecto.

  #### 2.1.1 ¿Qué es GitFlow?
 GitFlow es un modelo de ramificación (branching model) diseñado por Vincent Driessen que proporciona una estructura robusta para la gestión de proyectos a gran escala. A diferencia de otros flujos más simples, GitFlow asigna roles muy específicos a diferentes ramas, definiendo con precisión cuándo y cómo deben interactuar entre sí.

 Este modelo es ideal para proyectos que requieren un ciclo de lanzamiento organizado, ya que separa el trabajo en curso de la versión estable y probada.

 #### 2.1.2 Componentes del Modelo (Ramas)
En GitFlow, las ramas se dividen en dos categorías principales:

 - **Ramas Permanentes:**

   - **Main (o Master)**: Es la línea base de producción. Todo el código aquí es "sagrado", está probado y listo para el usuario final.

   - **Develop**: Es la rama de integración. Aquí es donde se reúnen todas las funcionalidades terminadas antes de pasar a producción.

- **Ramas de Apoyo (Transitorias):**

   - **Feature Branches:** Ramas temporales donde se desarrolla cada funcionalidad o sección del informe. Nacen de develop y vuelven a develop.

   - **Release Branches:** Se utilizan para preparar una nueva versión oficial (limpieza de errores, tildes, formato).

   - **Hotfix Branches:** Ramas de emergencia que nacen de main para corregir errores críticos sin interrumpir el trabajo en develop.

#### 2.1.3 Conceptos de Control de Versiones
- **Repositorio Distribuido:** A diferencia de los sistemas centralizados, cada integrante posee una copia completa del historial (gracias a Git), lo que permite trabajar sin conexión y con mayor seguridad.

- **Trazabilidad:** Es la capacidad de rastrear cada cambio hasta su origen (quién lo hizo, cuándo y por qué). En este informe, esto se evidencia en el historial de commits.

- **Integridad del Sistema:** Asegurada mediante el uso de Pull Requests, donde el contenido es supervisado antes de ser fusionado a la línea base.


### 2.2 Dinámica de Trabajo en GitFlow
A diferencia de otros modelos, GitFlow se basa en el uso de ramas con ciclos de vida definidos. Los desarrolladores trabajan en ramas de función aisladas y solo fusionan su código cuando la funcionalidad está completa y verificada. Esto garantiza que la rama principal siempre contenga código estable.

 #### Flujo General de Trabajo:
1. Se inicializa una rama develop desde main.
2. Se desprenden ramas feature desde develop para cada nueva tarea.
3. Al finalizar una feature, esta se fusiona nuevamente en develop.
4. Se crea una rama release desde develop para preparar el lanzamiento.
5. La release se fusiona en main (producción) y en develop.
6. Ante errores críticos en main, se utilizan ramas hotfix para reparaciones rápidas.


### 2.3 Implementación Práctica del Flujo de Trabajo