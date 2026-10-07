# AI Recipe from Available Ingredients

A responsive, dependency-free recipe finder with a curated local catalog. Ingredient matching, diet filters, and allergy exclusions run locally. There is no AI service configured; recipes still work from the catalog. Google Fonts use a network connection, with system-font fallbacks.

## Run

From the project directory, start a local web server:

```sh
python -m http.server 8000
```

Then visit http://localhost:8000. Serving over HTTP avoids browser restrictions on JavaScript modules loaded from file URLs.

## How it works

- Add ingredients individually, as comma-separated text, or from suggestions. Common spellings and synonyms are normalized in src/ingredients.js.
- Curated recipe data is in src/recipes.js. Required and optional ingredients are distinct.
- src/matching.js scores essential ingredient coverage (85% of the score) and optional ingredient coverage (15%). This percentage measures ingredient coverage, not the chance of recipe success.
- Dietary preferences and allergy exclusions are applied to the structured catalog before recommendations show. Substitutions are contextual ideas and are not allergy safety guarantees.
- Prep and cooking time are displayed separately. Recipe content is illustrative and should be reviewed before publication.

## Limitations

The small starter catalog is manually curated rather than an external licensed dataset. Review recipes and dataset licensing before expanding or redistributing a larger collection. Nutrition information and allergy checks are not professionally verified; users should check product labels and cross-contact details.
