## Kort refleksion

Jeg er tilfreds med, hvordan det som jeg har nået virker - jeg synes det efterligner prototypen så godt som muligt. 
Jeg har gjort mit bedste for at opsætte custom properties og global css - farver, gap og font-styles. Jeg ville dog gerne have nået mere og brugt flere (og mere avancerede) custom properties samt evt. flow-space-teknikken. 
Jeg synes jeg lykkedes godt med at bruge grid og subgrid til layoutet på siden, her med navngivne gridlines for at opnå større kontrol. Det er en teknik jeg gerne vil arbejde mere med, da jeg synes den har mange spændende muligheder!
Med komponententen "main-section" har jeg brugt Astro-props til at gøre indholdet dynamisk, men jeg har desværre ikke nået at bruge komponenten mere end ét sted. 

Jeg er ked af, at jeg ikke nåede længere med opgaven. Jeg har tendens til at være meget perfektionistisk på en stædig måde, hvor jeg har svært ved at slippe mindre vigtige detaljer og gå videre, selv når jeg ved, at der er vigtigere ting at fokusere på (og man kan jo altid vende tilbage senere). Det vil jeg gerne blive bedre til at administrere.

Jeg føler mig også nødsaget til at komme med en undskyldning for min arbejdsindsats, da jeg har været enormt begrænset pga. flytning inkl. renovering samt private udfordringer, der har fyldt enormt meget. 
Jeg er ved at "lande" igen, og jeg glæder mig til at kunne lægge den samme energi og tid i studiet igen, som jeg kunne for måned siden!:) 

Og til Dannie hvis du læser: forløbet du har undervist os i har været intensivt og virkelig spændende! Jeg er mega glad for alle de fantastiske CSS-muligheder som nu er en del af min "værktøjskasse", det er jeg oprigtigt begejstret for. På trods af min stressede og lidt begrænsede periode her i Oktober er jeg ved godt mod, og føler stadig jeg har godt overblik. 

# Opgaveskabelon til Frontend Design tema på Frontend-valgfaget

Se opgavebeskrivelsen på Fronter.

## Medfølgende Data

Der medfølger indholdsdata i form af lokale JSON-filer, som du kan bruge til din opgave. Det er ikke et krav til opgaven, men det kan gøre det nemmere og hurtigere at få tekst og billeder ind i dit projekt.

Bemærk, at CaseStudy-siden allerede inkluderer data fra en lokal JSON-fil.

Dokumentationen til anvendelsen af dataene finder du på: [https://frontend-design-theme.netlify.app/](https://frontend-design-theme.netlify.app/).

Her er et eksempel på, hvordan du kan bruge dataene i dine Astro-komponenter:

```astro
import employees from "@data/employees.json";

console.log(employees);
```

## Brug af hjælpekomponenter

### DynamicImage.astro

Brug denne komponent til at vise billeder dynamisk fra lokale datafiler. Du skal blot sende stien fra datasættet direkte til komponenten.

Eksempel med data:

```astro
{employees.map((employee) => (
  <DynamicImage
    imagePath={employee.img}
    altText={employee.name}
    width={200}
    height={200}
  />
))}
```

### DynamicIcon.astro

`DynamicIcon` bruges til at vise SVG-ikoner dynamisk baseret på et navn fra dine data.

Eksempel med data:

```astro
{employee.social_links.map((link) => (
  <DynamicIcon name={link.icon} />
))}
```

Her vises et ikon for hvert socialt medie, hvor `icon`-feltet matcher filnavnet på SVG-ikonet i `src/icons/`.

### HeroBgWrapper.astro

HeroBgWrapper bruges til Hero-sektioner på diverse undersider. Brug `imagePath` til at angive baggrundsbilledet. Du skal selv hente billederne fra Figma og lægge dem i mappen `src/assets/images`. Henvis derefter kun til filnavnet (f.eks. 'case.webp').

Alt markup du placerer mellem <HeroBgWrapper> og </HeroBgWrapper> bliver vist ovenpå baggrunden.

Eksempel:

```astro
<HeroBgWrapper imagePath="case.webp" class="hero-bg">
  <h1>Din overskrift</h1>
</HeroBgWrapper>
```

Du kan tilføje ekstra styling via `class` eller `style`-props, og alt indhold mellem tags bliver vist ovenpå baggrunden.

---

## Import af SVG-ikoner direkte

Du kan også importere SVG-ikoner direkte i dine komponenter, hvis du ønsker mere kontrol eller styling:

```astro
import Checkmark from "@icons/checkmark.svg";

<Checkmark width={32} height={32} class="my-icon" />
```

Se evt. `src/pages/svgs.astro` for flere eksempler på direkte import og brug af SVG-ikoner.
