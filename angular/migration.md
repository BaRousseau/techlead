# Migration

Document de travail pour migrer d'une version Angular à une autre.

## Aide à la migration Angular

<https://update.angular.io/>

## Changelog Angular

<https://github.com/angular/angular/blob/main/CHANGELOG.md>

## Migration Angular 10 vers 11

### Changelog 11

<https://v11.angular.io/guide/updating-to-version-11>

```bash
ng update @angular/core@11 @angular/cli@11 --allow-dirty --force
```

## Migration Angular 11 vers 12

### Changelog 12

<https://v12.angular.io/guide/updating-to-version-12>

```bash
ng update @angular/core@12 @angular/cli@12 --allow-dirty --force
```

## Migration Angular 12 vers 13

### Changelog 13

<https://v13.angular.io/guide/update-to-latest-version>

```bash
ng update @angular/core@13 @angular/cli@13 --allow-dirty --force
```

### Pour les auteurs de Schematics

```bash
npm i -D @schematics/angular@13
```

Dans les fichiers de schemas, remplacer `id` par `$id`.

Suppression de la partie lintFix.

## Migration Angular 13 vers 14

### Changelog 14

<https://v14.angular.io/guide/update-to-latest-version>

```bash
ng update @angular/core@14 @angular/cli@14 --allow-dirty --force
```

La target JavaScript monte en "es2020" par défaut.

Tous les FormControl deviennent des UntypedFormControl.

```ts
// AVANT
monBoolean = new FormControl(false);

// Temporairement avec UntypedFormControl
monBoolean = new UntypedFormControl(false);

// APRES avec non nullable value
monBoolean = new FormControl<boolean>(false, { nonNullable: true });

// APRES sans null
monBoolean = new FormControl<boolean>(false);
```

Si besoin Angular Material :

```bash
ng update @angular/material@14
```

## Migration Angular 14 vers 15

### Changelog 15

<https://v15.angular.io/guide/update-to-version-15>

```bash
ng update @angular/core@15 @angular/cli@15 --allow-dirty --force
```

Documentation officiel : <https://angular.io/guide/update-to-version-15>
Blog officiel : <https://blog.angular.io/angular-v15-is-now-available-df7be7f2f4c8>
Autre doc : <https://blog.ninja-squad.com/2022/11/16/what-is-new-angular-15.0/>
Standalone component : <https://angular.io/guide/standalone-components>

Attention, le nouveau moteur de rendu ViewEngine n'existe plus, il ne reste qu'Ivy.

La target JavaScript monte en "es2022" par défaut, mais c'est le fichier .browserlistrc qui indiquera réellement la target.

Par défaut, .browserlistrc est supprimé et Angular utilise un choix de navigateur par défaut.

Si besoin Angular Material :

```bash
ng update @angular/material@15

ng generate @angular/material:mdc-migration
```

Rechercher les `TODO(mdc-migration)`

### A partir d'Angular 15 (même avant), il est conseillé de migrer TSlint vers ESlint

```bash
ng add @angular-eslint/schematics --skip-confirmation
```

Rajouter le NOM_DU_PROJET à la fin de la commande suivante :

```bash
ng g @angular-eslint/schematics:convert-tslint-to-eslint --ignore-existing-tslint-config true --remove-tslint-if-no-more-tslint-targets true <NOM_DU_PROJET>
```

### Prettier

```bash
npm install --save-dev --save-exact prettier eslint-config-prettier eslint-plugin-prettier
```

Dans le fichier `.eslintrc.json`, rajouter "prettier" dans l'extends :

```json
{
  "root": true,
  "extends": ["prettier"]
}
```

A la racine, créer le fichier `.prettierrc` avec le contenu :

```json
{
  "singleQuote": true,
  "trailingComma": "none",
  "arrowParens": "avoid",
  "overrides": [
    {
      "files": "*.component.html",
      "options": {
        "parser": "angular"
      }
    },
    {
      "files": "*.html",
      "options": {
        "parser": "html"
      }
    }
  ]
}
```

A la racine, dupliquer le fichier `.gitignore` et renommer le nouveau fichier en `.prettierignore`.

Modifier le script `lint` du `package.json` :

```json
"lint": "prettier --check . && ng lint"
```

```bash
npx prettier --write .
```

Puis corriger manuellement avec :

```bash
npm run lint
```

### (optionnel) Configurer Prettier dans VSCode

- Install l'extension Prettier

Ouvrir un fichier TS, puis HTML, puis SCSS, puis JSONv, puis ...

- Ctrl + Shift + P
- "Format Document With"
- "Configure Default Formatter"
- "Prettier - Code Formatter"

## Standalone Component

Prérequis :

- Angular 15.2.0

<https://angular.io/guide/standalone-migration>

Run the migration in the order listed below, verifying that your code builds and runs between each step:

- Run ng g @angular/core:standalone and select "Convert all components, directives and pipes to standalone"
- Run ng g @angular/core:standalone and select "Remove unnecessary NgModule classes"
- Run ng g @angular/core:standalone and select "Bootstrap the project using standalone APIs"
- Run any linting and formatting checks, fix any failures, and commit the result

Find and remove any remaining NgModule declarations: since the "Remove unnecessary NgModules" step cannot remove all modules automatically, you may have to remove the remaining declarations manually.

- Run the project's unit tests and fix any failures.
- Run any code formatters, if the project uses automatic formatting.
- Run any linters in your project and fix new warnings. Some linters support a --fix flag that may resolve some of your warnings automatically.

## Migration Angular 15 vers 16

Documentation officiel : <https://angular.io/guide/update-to-version-16>
Blog officiel : <https://blog.angular.io/angular-v16-is-here-4d7a28ec680d>
Autre doc : <https://blog.ninja-squad.com/2023/05/03/what-is-new-angular-16.0/>

Prérequis :

- Node.js v16 ou v18

Changements :

- Angular Compatibility Compiler (ngcc) est supprimé !

```bash
ng update @angular/core@16 @angular/cli@16 --allow-dirty --force
```

## Migration Angular 16 vers 17

Documentation officiel : < TODO >
Blog officiel : <https://blog.angular.io/introducing-angular-v17-4d7033312e4b>
Autre doc : <https://blog.ninja-squad.com/2023/11/09/what-is-new-angular-17.0/>
Update Tool : <https://update.angular.io/?l=3&v=16.0-17.0>

Prérequis :

- Node.js v18 ou v20

Changements :

- Angular Signals
- Faster builds with the esbuild or 'application' builder <https://angular.io/guide/esbuild>
- New Control Flow (Developer preview)

```bash
ng update @angular/core@17 @angular/cli@17 --allow-dirty --force
```

## Angular Signals

<https://angular.io/guide/signals>
<https://blog.ninja-squad.com/2023/04/26/angular-signals/>

## New Control flow

Developer preview !

```bash
ng generate @angular/core:control-flow
```

## Deferrable views

Developer preview !

<https://blog.ninja-squad.com/2023/11/02/angular-defer/>

## Migration Angular 17 vers 18

<https://blog.ninja-squad.com/2024/05/22/what-is-new-angular-18.0/>

<https://medium.com/@yann.tho.le.moigne/angular-18-est-disponible-8be12070f399>
