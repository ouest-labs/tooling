# `@ouest-labs/tw-config`

Ce package offre une configuration TailwindCSS avancée, enrichie de plugins et d'utilitaires personnalisés pour améliorer les fonctionnalités de vos projets TailwindCSS. Les améliorations incluent des animations, une palette de couleurs étendue, et des adaptations réactives pour différents dispositifs.*

## Fonctionnalités

- **Couleurs Étendues** : Une palette de couleurs inspirée du Neobrutalisme pour des designs plus dynamiques.
- **Animations Personnalisées** : Animations spéciales pour les modaux, les infobulles, et les transitions de navigation.
- **Design Adaptatif** : Des points de rupture prédéfinis pour différentes tailles d'écran, des petits appareils aux grands écrans.
- **Plugins Intégrés** : Inclut des plugins essentiels tels que `@tailwindcss/forms`, `@tailwindcss/typography`, `tailwindcss-animate`, et `tailwindcss-radix`.

## Installation

Installez le package via npm :

```bash
npm install @ouest-labs/tw-config
```

## Utilisation

Pour utiliser cette configuration étendue dans votre projet TailwindCSS, importez-la dans votre fichier de configuration :

```ts
// tailwind.config.ts
import { Config } from "tailwindcss";
import extendedConfig from "@ouest-labs/tw-config";

const config: Config = {
  presets: [extendedConfig],
  // Vous pouvez ajouter ici vos configurations personnalisées
};

export default config;
```

## Détails de la Configuration

### Couleurs

Le package propose un ensemble unique de couleurs, allant d'une palette moderne inspirée du Neobrutalisme à des couleurs standard, pour améliorer vos capacités de design visuel.

### Animations

Profitez d'animations personnalisées telles que `scale-in`, `fade-in`, `wiggle`, etc., pour rendre vos interfaces utilisateur plus interactives et attrayantes.

### Design Réactif

Des points d'arrêt adaptés à tous les appareils assurent que votre projet reste responsive et accessible.

## Utilitaires Personnalisés

L'utilitaire `addVariablesForColors` ajoute des variables CSS pour toutes les configurations de couleurs, simplifiant la gestion des thèmes dans votre projet :

```typescript
function addVariablesForColors({ addBase, theme }: any) {
  let allColors = flattenColorPalette(theme("colors"));
  let newVars = Object.fromEntries(
    Object.entries(allColors).map(([key, val]) => [`--${key}`, val]),
  );

  addBase({
    ":root": newVars,
  });
}
```

## Contribuer

Les contributions sont toujours les bienvenues. Veuillez consulter les directives de contribution avant de soumettre vos modifications.

## Licence

Distribué sous la Licence MIT. Consultez le fichier [LICENSE] pour plus d'informations.
