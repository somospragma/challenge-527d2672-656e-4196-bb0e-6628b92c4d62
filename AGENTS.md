# Prompt para Mejorar el Codigo Base

Copia y pega el siguiente contenido completo en un asistente de IA (Claude, ChatGPT, etc.)
para obtener un ZIP con el proyecto arrancable. Si el adjunto es una carcasa (docs/placeholders),
el asistente debe materializar la estructura del stack del briefing, sin resolver las fases del reto.

---

```
## Briefing del reto (autoridad)
Este bloque manda sobre los archivos adjuntos. El stack y el rol salen de AQUÍ, no de un topic genérico ni de markdown placeholder.

### Perfil
Chapter Frontend, Especialidad Desarrollador, Tecnología Angular, Senior

### Brecha de conocimiento
Compara y aplica conscientemente al menos dos técnicas de renderizado web (CSR, SSR y pre-render) según el framework/librería y el contexto de negocio.

### Misión / candidato
Candidato con experiencia avanzada en Frontend, trabajando con Angular en contextos de alta complejidad.

### Reto
- Tema: Renderizado web
- Seniority: senior-l2
- Tipo: mixed
- Título: Técnicas de renderizado web en Angular
- Tiempo estimado: 4-5 horas

### Fases (trabajo del HUMANO — PROHIBIDO completarlas)
No implementes estos entregables. Dejalos como hueco pedagógico. El asistente solo materializa el proyecto arrancable para que el participante pueda trabajar.
- Fase 1: Comprender las técnicas de renderizado — objetivo: Entender las diferencias entre CSR, SSR y pre-render. — entregable (NO resolver): Documento comparativo de las técnicas de renderizado.
- Fase 2: Aplicar una técnica de renderizado — objetivo: Implementar una técnica de renderizado en una aplicación Angular. — entregable (NO resolver): Aplicación Angular con una técnica de renderizado implementada y documentación del proceso.
- Fase 3: Evaluar y comparar técnicas de renderizado — objetivo: Comparar el rendimiento y la experiencia del usuario entre diferentes técnicas de renderizado. — entregable (NO resolver): Comparación del rendimiento y la experiencia del usuario entre dos técnicas de renderizado.

Eres un asistente experto en análisis, corrección y generación de archivos de cualquier tipo:
código fuente, documentación, hojas de cálculo, documentos Word, configuraciones, entre otros.
Voy a enviarte una cadena de texto que contiene uno o más archivos. Cada archivo está delimitado por un marcador con el siguiente formato:
// === ARCHIVO: ruta/del/archivo.extension ===
o también puede aparecer como:
## === ARCHIVO: ruta/del/archivo.extension ===
Lo que sigue al marcador puede ser:

El contenido real del archivo (código, texto, YAML, etc.)
Una descripción en lenguaje natural de lo que debe contener el archivo


TU TAREA
PASO 1 — Detección y extracción
Identifica todos los archivos presentes en la cadena. Para cada archivo extrae:

Su ruta completa (ej: src/main/java/com/pragma/Service.java)
Su contenido o descripción

PASO 2 — Clasificación por tipo
Clasifica cada archivo en una de estas categorías:
A) Código fuente (Java, Python, TypeScript, JavaScript, Kotlin, etc.)
B) Configuración / documentación (YAML, properties, Markdown, JSON, txt, etc.)
C) Excel (.xlsx, .xls, .csv)
D) Word (.docx, .doc)
E) Otro tipo de archivo binario o especial
PASO 3 — Clasificación de errores en código fuente

Objetivo prioritario: que el proyecto compile. No corrijas flujo de negocio ni lógica funcional.

Antes de modificar cualquier archivo de código fuente, clasifica cada problema encontrado en una de estas dos categorías:
🔴 ERROR DE COMPILACIÓN — corregir siempre
Son errores que impiden que el proyecto arranque, sin valor pedagógico:

Import faltante o incorrecto
Clase, método o variable referenciada que no existe en ningún archivo del proyecto
Error de sintaxis
Anotación con atributos inválidos
Dependencia ausente en pom.xml, package.json, etc.
Archivo referenciado que no existe y debe ser creado con implementación mínima

→ CORREGIR estos errores.
🟡 PROBLEMA FUNCIONAL O DE CALIDAD — preservar siempre
Son problemas que no impiden compilar. Pueden ser intencionales para el aprendizaje:

Clave secreta hardcodeada ("secret", "password123")
API deprecada que funciona pero tiene reemplazo moderno
Lógica de negocio incorrecta o incompleta
Código redundante o de baja legibilidad
Falta de validaciones en flujo de negocio
Patrones de diseño incorrectos pero funcionales
Concurrencia no segura
Configuración funcional pero no óptima

→ PRESERVAR tal cual. No corregir, no mejorar, no comentar.
PASO 4 — Procesamiento según tipo de archivo
Tipo A — Código fuente
Aplica únicamente las correcciones clasificadas como 🔴 ERROR DE COMPILACIÓN.
No alteres ningún elemento clasificado como 🟡 PROBLEMA FUNCIONAL O DE CALIDAD.
Si falta un archivo referenciado, créalo con la implementación mínima necesaria para compilar.
Tipo B — Configuración / documentación
Extrae el contenido tal cual, sin modificaciones salvo errores evidentes de sintaxis
(ej: YAML mal indentado).
Tipo C — Excel (.xlsx)
Si viene con contenido real, genera el archivo respetando ese contenido.
Si viene con descripción en lenguaje natural, genera un archivo Excel funcional con:

Fila de encabezados en negrita con color de fondo distintivo
Columnas con ancho ajustado al contenido
Tipos de dato correctos por columna
Validaciones si la descripción lo indica
Hojas nombradas descriptivamente si hay más de una
Filas de ejemplo si no hay datos reales

Tipo D — Word (.docx)
Si viene con contenido real, genera el archivo respetando ese contenido.
Si viene con descripción en lenguaje natural, genera un documento Word funcional con:

Estilos de título (Título 1, Título 2) para jerarquía de secciones
Fuente legible (Calibri o equivalente), tamaño 11-12pt para cuerpo
Márgenes estándar
Tabla de contenido si tiene múltiples secciones
Tablas con encabezados en negrita si aplica

Tipo E — Otro
Genera el archivo con el contenido o estructura más apropiada según la descripción.
PASO 5 — Exportación en ZIP
Empaqueta todos los archivos en un único archivo ZIP descargable respetando exactamente
la estructura de rutas indicada por los marcadores.
El ZIP debe incluir:

Archivos de código con únicamente los errores de compilación corregidos
Archivos de configuración y documentación sin cambios
Archivos nuevos creados para resolver dependencias de compilación faltantes
Archivos Excel y Word generados desde descripción

IMPORTANTE: El ZIP debe estar listo para descargar al finalizar. No preguntes si el usuario
quiere generarlo. Simplemente genera el archivo y proporciona el enlace de descarga; No debes desplegar en el chat el resumen de lo que arreglaste al Zip, solo entregalo.

REGLAS IMPORTANTES

No omitas ningún archivo aunque no tenga errores ni modificaciones
Respeta los nombres y rutas exactas indicadas por los marcadores
Si un archivo no tiene marcador claro, infiere el nombre desde su contenido
Si la cadena contiene solo documentación o descripciones sin código, genera los archivos
correspondientes sin aplicar análisis de compilación
No agregues texto después del enlace de descarga del ZIP
No preguntes si el usuario quiere el ZIP: simplemente generalo siempre
Si detectas que falta un archivo de configuración necesario para compilar
(pom.xml, package.json, requirements.txt, build.gradle, etc.), créalo e inclúyelo
inferiendo su contenido desde los imports y frameworks detectados en el código
Nunca corrijas problemas 🟡 aunque parezcan obvios o fáciles de mejorar.
El participante que recibirá este proyecto los debe encontrar y resolver él mismo.


INPUT
Aquí está la cadena con los archivos:

import { NgModule } from '@angular/core';
import { BrowserModule } from '@angular/platform-browser';
import { AppComponent } from './app.component';

@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }

// === ARCHIVO: src/app/app.component.ts ===
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss']
})
export class AppComponent {
  title = 'Técnicas de renderizado web en Angular';
}

// === ARCHIVO: src/app/components/componente-ejemplo/componente-ejemplo.component.ts ===
import { Component } from '@angular/core';

@Component({
  selector: 'app-componente-ejemplo',
  template: `<p>Ejemplo de componente para demostración de renderizado.</p>`
})
export class ComponenteEjemploComponent { }

// === ARCHIVO: src/environments/environment.ts ===
export const environment = {
  production: false
};

// === ARCHIVO: src/styles/styles.scss ===
:root {
  --primary-color: #3f51b5;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
}

// === ARCHIVO: src/tests/renderizado.spec.ts ===
import { TestBed } from '@angular/core/testing';
import { AppComponent } from '../app.component';

describe('AppComponent', () => {
  beforeEach(async () => {
    await TestBed.configureTestingModule({
      declarations: [
        AppComponent
      ],
    }).compileComponents();
  });

  it('should create the app', () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app).toBeTruthy();
  });

  it(`should have as title 'Técnicas de renderizado web en Angular'`, () => {
    const fixture = TestBed.createComponent(AppComponent);
    const app = fixture.componentInstance;
    expect(app.title).toEqual('Técnicas de renderizado web en Angular');
  });
});

// === ARCHIVO: src/doc/comparacion-renderizado.md ===
# Comparación de técnicas de renderizado

## CSR (Client-Side Rendering)
- Ventajas: Interactividad inmediata, menos carga en el servidor.
- Desventajas: Mayor tiempo de carga inicial, SEO más complicado.

## SSR (Server-Side Rendering)
- Ventajas: Mejor SEO, menor tiempo de carga inicial.
- Desventajas: Mayor carga en el servidor, más compleja implementación.

## Pre-render
- Ventajas: Mejor SEO, menor tiempo de carga inicial.
- Desventajas: No interacciona con el usuario en tiempo real.

// === ARCHIVO: src/doc/implementacion-renderizado.md ===
# Implementación de una técnica de renderizado

## Pasos a seguir
1. Elegir una técnica de renderizado.
2. Configurar la aplicación Angular para usar la técnica elegida.
3. Documentar el proceso de implementación.

// === ARCHIVO: src/doc/evaluacion-renderizado.md ===
# Evaluación de técnicas de renderizado

## Comparación de rendimiento
- Medir el tiempo de carga y la interactividad de la página.

## Comparación de experiencia del usuario
- Recopilar feedback de usuarios sobre su experiencia con cada técnica.

// === ARCHIVO: angular.json ===
{
  "projects": {
    "renderizado-web": {
      "architect": {
        "build": {
          "builder": "@angular-devkit/build-angular:browser",
          "options": {
            "outputPath": "dist/renderizado-web",
            "index": "src/index.html",
            "main": "src/main.ts",
            "polyfills": "src/polyfills.ts",
            "tsConfig": "tsconfig.app.json",
            "assets": [
              "src/assets"
            ],
            "styles": [
              "src/styles/styles.scss"
            ],
            "scripts": []
          }
        }
      }
    }
  }
}

// === ARCHIVO: tsconfig.app.json ===
{
  "extends": "./tsconfig.json",
  "compilerOptions": {
    "outDir": "./out-tsc/app",
    "types": []
  },
  "files": [
    "src/main.ts",
    "src/polyfills.ts"
  ],
  "include": [
    "src/**/*.d.ts"
  ]
}

// === ARCHIVO: tsconfig.json ===
{
  "compileOnSave": false,
  "compilerOptions": {
    "baseUrl": "./",
    "outDir": "./dist/out-tsc",
    "sourceMap": true,
    "declaration": false,
    "downlevelIteration": true,
    "experimentalDecorators": true,
    "module": "esnext",
    "moduleResolution": "node",
    "importHelpers": true,
    "target": "es2015",
    "typeRoots": [
      "node_modules/@types"
    ],
    "lib": [
      "es2018",
      "dom"
    ]
  }
}

// === ARCHIVO: package.json ===
{
  "name": "renderizado-web",
  "version": "0.0.0",
  "scripts": {
    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e"
  },
  "private": true,
  "dependencies": {
    "~/angular/core": "17.0.0",
    "~/angular/platform-server": "17.0.0",
    "~/angular/common": "17.0.0",
    "~/angular/forms": "17.0.0",
    "~/angular/router": "17.0.0",
    "~/angular/animations": "17.0.0",
    "~/angular/http": "17.0.0"
  },
  "devDependencies": {
    "~/angular-in-memory-web-api": "17.0.0"
  }
}

// === ARCHIVO: src/main.ts ===
import { enableProdMode } from '@angular/core';
import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
import { AppModule } from './app/app.module';
import { environment } from './environments/environment';

if (environment.production) {
  enableProdMode();
}

platformBrowserDynamic().bootstrapModule(AppModule)
 .catch(err => console.error(err));
```
