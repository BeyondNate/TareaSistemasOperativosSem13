# Parte 1: Creación de Cuenta en GitHub

## Objetivo
Crear y configurar una cuenta de GitHub con medidas de seguridad adecuadas, incluyendo la autenticación de dos factores (2FA).

## Actividades Realizadas

### 1. Creación de la Cuenta
- Se ingresó al sitio web de GitHub.
- Se completó el proceso de registro con correo electrónico, nombre de usuario y contraseña segura.
- Se verificó la cuenta mediante el correo electrónico registrado.

### 2. Configuración de Autenticación Segura
- Se estableció una contraseña robusta y única.
- Se revisaron las opciones de seguridad de la cuenta.
- Se configuraron los datos básicos del perfil de usuario.

### 3. Activación de la Autenticación de Dos Factores (2FA)
- Se accedió a la configuración de seguridad de GitHub.
- Se habilitó la autenticación de dos factores (2FA).
- Se vinculó una aplicación autenticadora.
- Se guardaron los códigos de recuperación en un lugar seguro.

## Evidencias

### Evidencia 1: Cuenta Creada

### Evidencia 2: Activación de 2FA

### Evidencia 3: Perfil Configurado

![Perfil configurado](https://github.com/BeyondNate/TareaSistemasOperativosSem13/blob/6f0240cbcb699109f16887cc84a3954b671715be/Cuentas_GitHub/Imagenes/perfil_Paola.png)

---

## Conclusión

Se completó satisfactoriamente la creación de la cuenta en GitHub, la configuración de seguridad mediante una contraseña segura y la activación de la autenticación de dos factores (2FA), garantizando una mayor protección de la cuenta.


# Parte 2: Instalación y Configuración de Git en Linux

## Objetivo
Instalar Git en un sistema Linux (Ubuntu/Debian) y realizar la configuración inicial del usuario para el control de versiones.

## Instalación de Git

### Actualizar los repositorios del sistema

```bash
sudo apt update
```

### Instalar Git

```bash
sudo apt install git
```

### Verificar la instalación

```bash
git --version
```

**Resultado esperado:**

```bash
git version X.X.X
```

---

## Configuración Inicial de Git

### Configurar nombre de usuario

```bash
git config --global user.name "Nombre Apellido"
```

### Configurar correo electrónico

```bash
git config --global user.email "correo@ejemplo.com"
```

### Verificar la configuración

```bash
git config --list
```

**Resultado esperado:**

```bash
user.name=Nombre Apellido
user.email=correo@ejemplo.com
...
```

---

## Evidencia

### Captura de la Configuración Realizada

**Captura de pantalla:**
*(Insertar aquí la captura mostrando la ejecución de `git config --list` con los datos configurados)*

![Configuración de Git](ruta/de/la/imagen.png)

---

## Conclusión

Se instaló correctamente Git en el sistema Linux y se realizó la configuración inicial del usuario, estableciendo el nombre y correo electrónico que serán utilizados para identificar los cambios realizados en los repositorios.
