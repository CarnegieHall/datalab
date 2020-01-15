# maps

a testing page for maps!

<iframe 
style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fperson%20%3FpersonLabel%20%3FpersonImage%20%3FbirthPlaceLabel%20%3Flocation%20%28YEAR%28%3Fdate%29%20as%20%3Fyear%29%0A%28IRI%28CONCAT%28%22http%3A%2F%2Fdata.carnegiehall.org%2Fnames%2F%22%2C%28STR%28%3FchAgent_id%29%29%29%29%20AS%20%3FchLOD%29%0AWHERE%0A%7B%0A%20%20%20%20BIND%28MONTH%28NOW%28%29%29%20AS%20%3FnowMonth%29%0A%20%20%20%20BIND%28DAY%28NOW%28%29%29%20AS%20%3FnowDay%29%0A%0A%20%20%20%20%3Fperson%20wdt%3AP569%20%3Fdate%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP19%20%3FbirthPlace%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP4104%20%3FchAgent_id%20.%0A%20%20%20%20%3FbirthPlace%20wdt%3AP625%20%3Flocation%20.%0A%20%20%20%20FILTER%20%28MONTH%28%3Fdate%29%20%3D%20%3FnowMonth%20%26%26%20DAY%28%3Fdate%29%20%3D%20%3FnowDay%29%0A%20%20%20%20OPTIONAL%20%7B%20%3Fperson%20wdt%3AP18%20%3FpersonImage%20%7D%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22.%20%7D%0A%0A%7D%0AORDER%20BY%20%3Fyear%0ALIMIT%20100" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" >

[visualization or representative image/icon]

## EXPERIMENT LABEL/TITLE
disambiguated, human-understandable label for experiment

## SUMMARY/OVERVIEW
- briefly state purpose of experiment, what question is being answered
- identify scope and result
- written for general audience, e.g., can be used for social media caption

## METHODS
- what we did to build the experiment
- what tools, data, languages, or other resources were used

## CONCLUSIONS
### what we learned
- summarize, add date for appended thoughts

### further investigation 
- things we could not figure out/tool limitations
- link to open GH Issues (if applicable)
