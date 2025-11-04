# GotaGris - Landing Page

## Documentación de Optimización de Imágenes

### Criterios de Selección de Imágenes

#### 1. Especificaciones Técnicas
- **Formato primario**: AVIF (mejor compresión, soporte moderno)
- **Formato secundario**: WebP (excelente compresión, amplio soporte)
- **Formato fallback**: JPG (compatibilidad universal)
- **Tamaño máximo**: 100KB por imagen comprimida
- **Dimensiones**: 120x120px para info-cards
- **Aspect ratio**: 1:1 (cuadrada)

#### 2. Criterios de Contenido por Sección

##### Card 1: "Nuestra Misión en GotaGris"
- **Imagen sugerida**: `mision-gotagris.*`
- **Contenido visual**: Agua gris siendo recolectada, sostenibilidad ambiental
- **Paleta de colores**: Tonos verdes y azules (agua/naturaleza)
- **Elementos clave**: Gotas de agua, plantas, sostenibilidad

##### Card 2: "Beneficios para el Agricultor"
- **Imagen sugerida**: `beneficios-agricultor.*`
- **Contenido visual**: Pequeños agricultores trabajando con herramientas modernas
- **Paleta de colores**: Tierra, verde agricultura, tonos cálidos
- **Elementos clave**: Agricultor, plantas creciendo, productividad

##### Card 3: "Proceso de Agua Gris"
- **Imagen sugerida**: `proceso-agua-gris.*`
- **Contenido visual**: Sistema de filtración o tubería de agua
- **Paleta de colores**: Azul agua, metálicos, limpieza
- **Elementos clave**: Tuberías, filtros, agua clara

#### 3. Implementación Técnica

##### Estructura de Archivos
```
assets/img/info-cards/
├── mision-gotagris.avif
├── mision-gotagris.webp
├── mision-gotagris.jpg
├── beneficios-agricultor.avif
├── beneficios-agricultor.webp
├── beneficios-agricultor.jpg
├── proceso-agua-gris.avif
├── proceso-agua-gris.webp
└── proceso-agua-gris.jpg
```

##### Optimización por Formato
- **AVIF**: Compresión lossy, calidad 70-80
- **WebP**: Compresión lossy, calidad 75-85
- **JPG**: Compresión optimizada, calidad 80-90

#### 4. Características de Rendimiento

##### Lazy Loading
- Implementado con `loading="lazy"`
- Skeleton loader para mejorar UX durante carga
- Prefetch para imágenes above-the-fold

##### Accesibilidad
- Atributos `alt` descriptivos y contextuales
- Dimensiones intrínsecas para evitar layout shift
- Soporte para lectores de pantalla

##### Cross-browser Compatibility
- Elemento `<picture>` con múltiples sources
- Fallbacks automáticos JPG → WebP → AVIF
- Polyfills CSS para `aspect-ratio` en navegadores legacy

#### 5. Testing de Performance

##### Métricas Objetivo Lighthouse
- **Performance**: ≥90
- **Accessibility**: ≥95
- **Best Practices**: ≥90
- **SEO**: ≥90

##### Core Web Vitals
- **LCP**: < 2.5s (imagen optimizada contribuye)
- **FID**: < 100ms
- **CLS**: < 0.1 (dimensiones fijas previenen shifts)

#### 6. Dark/Light Mode

##### Compatibilidad Visual
- Skeleton loaders adaptativos según tema
- Sombras ajustadas para contraste óptimo
- Bordes que respetan preferencias de color del sistema

#### 7. Herramientas de Compresión Recomendadas

##### Para Desarrollo
- **ImageOptim** (macOS)
- **TinyPNG** (Web)
- **Squoosh** (Google, Web)
- **ImageMin** (CLI, automatización)

##### Para CI/CD
```bash
# Ejemplo de compresión automatizada
imagemin assets/img/info-cards/*.jpg --out-dir=dist/img/info-cards/ --plugin=imagemin-mozjpeg
cwebp -q 80 assets/img/info-cards/*.jpg -o assets/img/info-cards/
```

#### 8. Monitoreo y Mantenimiento

##### Auditoría Regular
- Revisión mensual de tamaños de archivo
- Testing cross-browser en dispositivos reales
- Monitoreo de Core Web Vitals en producción
- Validación de accesibilidad con herramientas automatizadas

##### KPIs de Imagen
- Tiempo de carga promedio < 1s
- Tasa de error de carga < 1%
- Satisfacción de usuario (bounce rate relacionado)

## Comando de Instalación

```bash
# Instalar dependencias de optimización
npm install imagemin imagemin-avif imagemin-webp imagemin-mozjpeg --save-dev
```

---

**Última actualización**: Noviembre 2025  
**Autor**: Equipo de Desarrollo GotaGris  
**Revisión**: Performance Frontend Specialist