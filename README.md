# 👋 Hola Mundo — Java 17 + Gradle

Aplicación mínima de ejemplo que muestra cómo:
- Estructurar un proyecto Java con Gradle
- Generar instaladores nativos para Linux, macOS y Windows usando GitHub Actions

## 🚀 Ejecutar en local

```bash
# Compilar
./gradlew build

# Ejecutar
./gradlew run
```

## 📦 Generar instaladores

Los instaladores se generan **automáticamente** en GitHub Actions.

### Opción A — Crear un release (recomendado)
```bash
git tag v1.0.0
git push origin v1.0.0
```
Esto dispara el workflow y publica los instaladores en la pestaña **Releases** de GitHub.

### Opción B — Lanzar manualmente
Ve a **Actions → Build Installers → Run workflow**

## 📁 Estructura del proyecto

```
holamundo/
├── src/main/java/com/ejemplo/holamundo/
│   └── Main.java                    ← Código fuente
├── .github/workflows/
│   └── build.yml                    ← Pipeline de CI/CD
├── build.gradle                     ← Configuración del proyecto
├── settings.gradle                  ← Nombre del proyecto
└── gradlew / gradlew.bat            ← Gradle Wrapper
```

## 🔧 Instaladores generados

| OS | Formato | Uso |
|----|---------|-----|
| Linux | `.deb` | `sudo dpkg -i holamundo.deb` |
| Linux | `.rpm` | `sudo rpm -i holamundo.rpm` |
| Linux | `.sh` | `bash instalar-holamundo.sh` |
| macOS | `.dmg` | Doble clic y arrastra a Aplicaciones |
| macOS | `.pkg` | Instalación silenciosa |
| Windows | `.exe` | Doble clic, asistente de instalación |
| Windows | `.msi` | Despliegue empresarial vía GPO |
