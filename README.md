# 📘 Guía práctica para aprender Git en equipo

Un ejercicio paso a paso para aprender Git simulando trabajo colaborativo, manejo de ramas, resolución de conflictos y sincronización con GitHub.

---

## 📁 Tabla de contenidos

1. [🎯 Objetivo](#🎯-objetivo)
2. [📋 Instalación y Configuración Inicial](#📋-paso-1-instalación-y-configuración-inicial)
3. [📁 Crear Proyecto y Repositorio Local](#📁-paso-2-crear-proyecto-y-repositorio-local)
4. [🌿 Trabajo con Ramas](#🌿-paso-3-trabajo-con-ramas-branches)
5. [🔄 Fusionar Cambios](#🔄-paso-4-fusionar-cambios-merge)
6. [⚡ Simular y Resolver Conflictos](#⚡-paso-5-simular-y-resolver-conflictos)
7. [🌐 Repositorio Remoto](#🌐-paso-6-opcional-repositorio-remoto)
8. [🤔 Reflexión y Aprendizajes](#🤔-reflexión-y-aprendizajes)
9. [📚 Comandos Git Aprendidos](#📚-comandos-git-aprendidos)
10. [🔗 Recursos Adicionales](#🔗-recursos-adicionales)

---

## 🎯 Objetivo

Aprender a usar Git para gestionar versiones de proyectos, simulando trabajo colaborativo en equipo.

---

## 📋 Paso 1: Instalación y Configuración Inicial

### 1.1 Instalar Git

* **Windows/Mac/Linux**: Descargar desde [https://git-scm.com](https://git-scm.com)
* Seguir el instalador con opciones por defecto

### 1.2 Verificar la instalación

```bash
git --version
```

**Resultado esperado**: `git version 2.x.x`

### 1.3 Configurar identidad global

```bash
git config --global user.name "Tu Nombre Completo"
git config --global user.email "tu.email@ejemplo.com"
```

### 1.4 Verificar configuración

```bash
git config --list
```

---

## 📁 Paso 2: Crear Proyecto y Repositorio Local

### 2.1 Crear estructura del proyecto

```bash
mkdir guia-bienvenida
cd guia-bienvenida
git init
```

### 2.2 Crear archivo inicial

```bash
echo "Bienvenido al equipo DevSoft!" > bienvenida.txt
```

### 2.3 Verificar estado y hacer primer commit

```bash
git status
git add bienvenida.txt
git commit -m "Primer commit: se crea archivo de bienvenida"
```

---

## 🌿 Paso 3: Trabajo con Ramas (Branches)

### 3.1 Crear y cambiar a nueva rama

```bash
git branch estilo
git checkout estilo
git branch
```

### 3.2 Modificar archivo en la nueva rama

```bash
echo "Recuerda seguir nuestra guía de estilo para escribir documentos." >> bienvenida.txt
cat bienvenida.txt
```

### 3.3 Commit en la rama `estilo`

```bash
git add bienvenida.txt
git commit -m "Agrega recomendaciones de estilo"
```

---

## 🔄 Paso 4: Fusionar Cambios (Merge)

### 4.1 Volver a rama `main`

```bash
git checkout main
cat bienvenida.txt
```

### 4.2 Fusionar rama `estilo` en `main`

```bash
git merge estilo
cat bienvenida.txt
```

### 4.3 Ver historial de commits

```bash
git log --oneline
git log --graph --oneline --all
```

---

## ⚡ Paso 5: Simular y Resolver Conflictos

### 5.1 Crear nueva rama con cambios

```bash
git checkout -b bienvenida-equipo
echo "Hola! Te damos la más cordial bienvenida al equipo de desarrollo." > bienvenida.txt
echo "Recuerda seguir nuestra guía de estilo para escribir documentos." >> bienvenida.txt
git add bienvenida.txt
git commit -m "Cambia saludo de bienvenida"
```

### 5.2 Crear conflicto en rama `main`

```bash
git checkout main
echo "Bienvenido a DevSoft, estamos felices de tenerte aquí." > bienvenida.txt
echo "Recuerda seguir nuestra guía de estilo para escribir documentos." >> bienvenida.txt
git add bienvenida.txt
git commit -m "Modifica saludo en rama main"
```

### 5.3 Intentar fusionar (generará conflicto)

```bash
git merge bienvenida-equipo
```

**¡Aparecerá un conflicto!** Git mostrará el archivo con marcas como estas:

```
<<<<<<< HEAD
Bienvenido a DevSoft, estamos felices de tenerte aquí.
=======
Hola! Te damos la más cordial bienvenida al equipo de desarrollo.
>>>>>>> bienvenida-equipo
Recuerda seguir nuestra guía de estilo para escribir documentos.
```

### 5.4 Resolver el conflicto

```bash
echo "¡Bienvenido a DevSoft, el equipo te da una cálida bienvenida!" > bienvenida.txt
echo "Recuerda seguir nuestra guía de estilo para escribir documentos." >> bienvenida.txt
git add bienvenida.txt
git commit -m "Resuelve conflicto en mensaje de bienvenida"
```

---

## 🌐 Paso 6 (Opcional): Repositorio Remoto

### 6.1 Crear repositorio en GitHub

1. Ir a [GitHub.com](https://github.com)
2. Crear nuevo repositorio llamado `guia-bienvenida`
3. No inicializar con README

### 6.2 Conectar repositorio local con remoto (HTTPS)

```bash
git remote add origin https://github.com/TUUSUARIO/guia-bienvenida.git
git push -u origin main
```

---

## 🤔 Reflexión y Aprendizajes

### Preguntas de Reflexión:

1. ¿Qué fue lo más desafiante al trabajar con ramas y fusiones?
2. ¿Por qué son importantes los commits frecuentes con mensajes claros?
3. ¿Cómo Git ayuda a evitar conflictos en trabajo colaborativo?
4. ¿Qué aprendiste sobre manejo de conflictos?
5. ¿En qué proyectos aplicarías Git?

---

## 📚 Comandos Git Aprendidos

| Comando        | Descripción                     |
| -------------- | ------------------------------- |
| `git init`     | Inicializar repositorio         |
| `git add`      | Agregar archivos al staging     |
| `git commit`   | Guardar cambios permanentemente |
| `git status`   | Ver estado del repositorio      |
| `git branch`   | Crear/listar ramas              |
| `git checkout` | Cambiar de rama                 |
| `git merge`    | Fusionar ramas                  |
| `git log`      | Ver historial de commits        |
| `git remote`   | Gestionar repositorios remotos  |
| `git push`     | Subir cambios al remoto         |

---

## 🌟 ¡Felicitaciones!

Has completado tu primer ejercicio completo con Git. Ahora dominas los fundamentos para:

* ✅ Gestionar versiones de tus proyectos
* ✅ Trabajar colaborativamente con ramas
* ✅ Resolver conflictos de manera efectiva
* ✅ Sincronizar con repositorios remotos

### 📋 Entregable

**Comparte tu principal aprendizaje sobre Git para trabajo colaborativo y gestión de versiones.**

---

## 🔗 Recursos Adicionales

* [Documentación oficial de Git](https://git-scm.com/doc)
* [GitHub Learning Lab](https://lab.github.com/)
* [Visualización interactiva de Git](https://learngitbranching.js.org/)
