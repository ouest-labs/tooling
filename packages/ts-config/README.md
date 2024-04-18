# `@ouest-labs/tsconfig`

Ce package fournit des configurations TypeScript optimisées pour différents environnements de développement comme **Next.js** et les **bibliothèques React**. Chaque configuration est conçue pour offrir les meilleures pratiques et garantir la cohérence dans vos projets TypeScript.

## Configurations disponibles

### Base Configuration (`base.json`)

La configuration de base définit des règles strictes pour TypeScript, garantissant des pratiques de codage robustes et sécurisées.
*

```json
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "compilerOptions": {
    "declaration": true,
    "declarationMap": true,
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "noEmit": true,
    "isolatedModules": true,
    "moduleResolution": "node",
    "strict": true,
    "strictNullChecks": true
  },
  "exclude": ["node_modules"]
}
```

### Next.js Configuration (`nextjs.json`)

Adaptée pour les projets Next.js, cette configuration permet une intégration fluide avec des ajustements spécifiques pour la plateforme.

```json
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "extends": "./base.json",
  "compilerOptions": {
    "plugins": [{ "name": "next" }],
    "allowJs": true,
    "jsx": "preserve",
    "lib": ["dom", "dom.iterable", "esnext"],
    "module": "esnext",
    "resolveJsonModule": true,
    "target": "es5"
  },
  "include": ["src", "next-env.d.ts"],
  "exclude": ["node_modules"]
}
```

### React Library Configuration (`react-library.json`)

Idéale pour le développement de bibliothèques React, elle configure TypeScript pour une compatibilité optimale avec les composants React modernes.

```json
{
  "$schema": "https://json.schemastore.org/tsconfig",
  "extends": "./base.json",
  "compilerOptions": {
    "lib": ["ES2018", "dom"],
    "module": "ESNext",
    "target": "ES6",
    "jsx": "react-jsx",
    "noEmit": true
  }
}
```

## Installation

Pour intégrer ces configurations TypeScript dans votre projet, installez le package via npm :

```bash
npm install @ouest-labs/tsconfig
```

## Utilisation

Pour utiliser une des configurations dans votre projet, spécifiez l'extension dans votre `tsconfig.json` :

```json
{
  "extends": "@ouest-labs/tsconfig/base.json"
}
```

## Licence

Distribué sous la Licence MIT.
