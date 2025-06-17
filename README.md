# Automatización de pruebas con GitHub Actions

## Preguntas y Respuestas

### 1. ¿Qué ventajas observaste al automatizar pruebas con GitHub Actions?

- **Integración nativa con GitHub:** No requiere configuraciones adicionales ni instalaciones externas.
- **Automatización inmediata:** Se ejecutan pruebas automáticamente al hacer push o pull request a la rama `main`.
- **Feedback rápido:** Detecta errores de forma temprana en el proceso de desarrollo.
- **Entorno reproducible:** Usa entornos controlados (como `ubuntu-latest`) asegurando que las pruebas corran de forma consistente.
- **Escalabilidad y facilidad de uso:** Permite definir múltiples jobs y matrices para diferentes versiones de Node.js sin complicaciones.

### 2. ¿Qué diferencia a GitHub Actions de Jenkins u otras herramientas CI?

| Característica        | GitHub Actions                     | Jenkins                          |
|-----------------------|------------------------------------|-----------------------------------|
| Integración           | Nativa con GitHub                  | Requiere configuración externa    |
| Configuración         | YAML en el repo                    | Configuración UI o Jenkinsfile    |
| Escalabilidad         | Escalable usando runners           | Escalable, pero requiere mantenimiento propio |
| Infraestructura       | Basada en la nube (por defecto)    | Requiere servidor propio o cloud |
| Facilidad de uso      | Muy intuitivo para proyectos GitHub| Requiere curva de aprendizaje     |

### 3. ¿Qué mejoras podrías agregar a este pipeline?

- **Linting automático** con ESLint o Prettier.
- **Cobertura de pruebas** con herramientas como `jest --coverage` o `nyc`.
- **Deploy automático** a ambientes de prueba o producción.
- **Soporte para múltiples versiones de Node.js** mediante una matriz.
- **Caché de dependencias** para acelerar los tiempos de build.
- **Notificaciones** en Slack o Discord ante fallos o despliegues exitosos.

### 4. ¿Qué consideraciones de seguridad aplicarías en proyectos reales?

- **Usar Secrets en lugar de variables en texto plano:** como `NODE_ENV`, tokens, claves API, etc.
- **Limitar accesos a Secrets:** solo workflows necesarios deben acceder.
- **Verificar dependencias:** usar herramientas como `npm audit` o `Snyk`.
- **Revisar permisos del workflow:** por defecto los workflows tienen acceso de escritura; conviene limitarlo.
- **Evitar ejecuciones en ramas inseguras o forks desconocidos.**
- **Firmar commits o usar acciones verificadas** (acciones oficiales o de confianza).

---