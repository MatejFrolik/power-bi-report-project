# Power BI report projekt

## Populace ve světě, Evropě a České republice

Odkaz na můj **Linkedln** [ZDE](https://www.linkedin.com/in/mat%C4%9Bj-frol%C3%ADk-183812230/) 

-------

### Úvod do projektu
Cílem reportu je vyobrazení historického počtu obyvatel ve světě, Evropě a České republice. Počet obyvatel jednotlivých států evropské unie, podíl cizinců a hustotu zalidnění. V poslední řadě detailní pohled na obyvatelstvo v České republice, krajích a krajských měst České republiky.

### Jednotlivé kroky projektu
1. Získání potřebných datových sad z portálu _data.gov.cz_ a dalších stránek s otevřenými daty do souboru CSV..
2. Načtení tabulek s daty do prostředí Power BI a jejich úprava v PowerQuery.
3. Vytvoření nové measure počítající součet populace jednotlivých zemí a nového sloupce density_per_km ukazující počet obyvatel na kilometr čtvereční v tabulce population_europe_countries.
4. Vytvoření hiearchie v tabulce population_europe_history pomocí DAX. 
```
part_of_Europe = 
IF( 
    population_europe_countries[country] 
    IN{"United Kingdom",
    "France", "Belgium","Netherlands","Luxembourg","Ireland","Monaco"}, "West Europe",
    IF(
        population_europe_countries[country]
        IN{"Russia","Ukraine","Belarus","Moldova"},"East Europe",
        IF(
            population_europe_countries[country]
            IN{"Sweden","Denmark","Finland","Norway", "Iceland","Lithuania","Latvia","Estonia"},"North Europe",
            IF(
                population_europe_countries[country]
                IN{"Austria","Czech Republic (Czechia)","Germany","Hungary","Poland","Liechtenstein","Slovakia","Slovenia",
                "Switzerland"},"Central Europe",
                IF(
                    population_europe_countries[country]
                    IN{"Albania","Andorra","Bosnia and Herzegovina","Bulgaria","Croatia","Greece","Italy","Malta","Portugal",
                    "Romania","San Marino","Slovenia","Spain","North Macedonia","Serbia","Montenegro"},"South Europe","European islands"
)))))
```
stejný postup u vytvoření hiearchie v tabulce population_czech_region
5. Vytvoření třech stránek pro zobrazení populace ve světě, v Evropě a v České republice.
6. Přidání grafických vizuálů pro zobrazení dat. (tables, pie, line, columns chart, cards...)
7. Přidání slicerů na jednotlivé stránky pro filtrování dat vytvoření bookmarks/page navigation pro jednodušší pohyb po stránkách.
8. Závěrečná grafická úprava reportu.


### obrázky

<br />

![My Image](název.png)

