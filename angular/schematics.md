# Schematics

## Ressources

[Doc officielle](https://angular.io/guide/schematics-authoring#authoring-schematics)
[Blog](https://blog.angular.io/schematics-an-introduction-dc1dfbc2a2b2)
[Vidéos Tuto](https://www.youtube.com/watch?v=M5YSPas3qFo)
[Repo Schematics Angular](https://github.com/angular/angular-cli/tree/main/packages/schematics/angular/application)
[Different ways to run schematics from another schematics](https://angularindepth.com/posts/1453/different-ways-to-run-schematics-from-the-schematic)
[Schematics Playground](https://github.com/d-koppenhagen/schematics-helpers-playground)

## Ask Confirmation Example

```ts
import { askConfirmation } from '@angular/cli/utilities/prompt';

export function yourSchematicsFn(options: Schema): Rule {
    return async (tree: Tree, context: SchematicContext) => {
         const includeBanner = await askConfirmation('Include Banner?', true);
         if(includeBanner) {
              // ask for bannerTitle and bannerDescription
         }
         else {
              // do something else
         }
         return chain(/* chain your rules here */);
    }
}
```
