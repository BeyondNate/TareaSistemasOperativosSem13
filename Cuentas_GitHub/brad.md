
# INFORME FINAL DE SEGURIDAD: GESTIÓN DE EVIDENCIAS
**Curso:** Sistemas Operativos  
**Estudiante:** Brad Cárdenas
**Fecha:** Junio 2026  

---

## 1. Amenazas Identificadas y Matriz de Riesgo

Durante el desarrollo de prácticas en entornos compartidos (como laptops prestadas o laboratorios públicos), la información y las evidencias de evaluación están expuestas a las siguientes amenazas de seguridad:

* **Acceso no autorizado:** Exposición de archivos locales a otros usuarios que utilicen la misma máquina física, permitiendo el espionaje, copia o alteración maliciosa de las actividades.
* **Robo de credenciales:** Intercepción de contraseñas o tokens de acceso si se introducen directamente en texto plano en navegadores o terminales de uso público.
* **Modificación de archivos:** Alteración maliciosa o accidental de los reportes y códigos de las prácticas, lo que invalidaría la autoría o destruiría el trabajo realizado.
* **Divulgación de información:** Publicación accidental de datos sensibles en repositorios abiertos a todo el internet, exponiendo la propiedad intelectual y configuraciones internas del sistema.

---

## 2. Medidas de Seguridad Implementadas (Contramedidas)

Para mitigar las amenazas descritas, se aplicó un enfoque de seguridad en capas (Defensa en Profundidad) utilizando las siguientes herramientas:

### A. Seguridad a Nivel de Sistema Operativo Local (Linux)
* **Permisos Linux:** Se validó el aislamiento de entornos mediante el esquema estándar de privilegios de usuario (`rwx`). Las evidencias se mantuvieron dentro del directorio del usuario correspondiente para restringir el acceso a terceros.
* **Listas de Control de Acceso (ACL):** Se utilizaron para garantizar que únicamente los usuarios explícitamente autorizados en el sistema operativo local pudiesen interactuar con los directorios de trabajo, superando las limitaciones del esquema tradicional de permisos de Linux.

### B. Control de Versiones Seguro y Autenticación (Git & GitHub)
* **Uso de Git:** Permite mantener un historial detallado, inmutable y auditable de cada cambio en el proyecto mediante commits firmados con un autor específico (`user.name` y `user.email`), evitando el repudio de la información.
* **Autenticación de Dos Factores (2FA):** Activada globalmente en la cuenta de GitHub. Aunque un atacante intercepte la contraseña de la cuenta, no puede iniciar sesión sin el segundo factor dinámico (OTP/Aplicación de autenticación).
* **Protocolo SSH (Secure Shell):** Se generaron llaves criptográficas asimétricas (`ed25519`). La autenticación con el servidor remoto se realiza mediante el intercambio de la clave pública, eliminando por completo la necesidad de escribir contraseñas en texto plano en la terminal de la laptop prestada.
* **GitHub Privado:** El repositorio se configuró estrictamente como **Privado**, mitigando el riesgo de divulgación. El acceso se limitó exclusivamente al estudiante y al docente con rol restrictivo de **Solo Lectura (Read)** bajo el principio de menor privilegio.

### C. Mecanismos de Protección de Datos y Criptografía
* **Archivo `.gitignore`:** Se implementó como control preventivo para listar extensiones y archivos críticos (`*.key`, `passwords.txt`, `*.pem`, `*.crt`, `*.log`). Esto evita que Git rastree o publique accidentalmente credenciales en la nube.
* **Control de Integridad (Hash SHA-256):** Se calculó la huella digital criptográfica del documento final mediante el algoritmo `sha256sum`, guardando el resultado en `hashes.txt`. Esto garantiza que cualquier intento de modificación posterior del archivo alterará el hash, permitiendo detectar inmediatamente la pérdida de integridad.

---

## 3. Conclusiones y Buenas Prácticas de Cierre

Como control definitivo de la práctica y mitigación crítica frente al uso de una **laptop prestada**, se procedió con un protocolo de sanitización al finalizar la entrega:
1. Eliminación completa del árbol de directorios local (`rm -rf`).
2. Destrucción definitiva de las llaves privadas del sistema local (`rm -rf ~/.ssh`).
3. Limpieza de las variables globales de Git en la terminal para no dejar rastro de identidad.
4. Cierre forzado de sesiones en el navegador web.

Este flujo de trabajo garantiza que el ciclo de vida del desarrollo y almacenamiento de evidencias cumple con los estándares actuales de confidencialidad, integridad y disponibilidad exigidos en la administración de Sistemas Operativos seguros.
