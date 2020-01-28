# chdl-0001-a

## Whose birthday is today?

A birthplace map of performers and composers from Carnegie Hall's performance history. 

<figure class="map_container">
  <iframe style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fperson%20%3FpersonLabel%20%3FpersonImage%20%3FbirthPlaceLabel%20%3Flocation%20%28YEAR%28%3Fdate%29%20as%20%3Fyear%29%0A%28IRI%28CONCAT%28%22http%3A%2F%2Fdata.carnegiehall.org%2Fnames%2F%22%2C%28STR%28%3FchAgent_id%29%29%29%29%20AS%20%3FchLOD%29%0AWHERE%0A%7B%0A%20%20%20%20BIND%28MONTH%28NOW%28%29%29%20AS%20%3FnowMonth%29%0A%20%20%20%20BIND%28DAY%28NOW%28%29%29%20AS%20%3FnowDay%29%0A%0A%20%20%20%20%3Fperson%20wdt%3AP569%20%3Fdate%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP19%20%3FbirthPlace%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP4104%20%3FchAgent_id%20.%0A%20%20%20%20%3FbirthPlace%20wdt%3AP625%20%3Flocation%20.%0A%20%20%20%20FILTER%20%28MONTH%28%3Fdate%29%20%3D%20%3FnowMonth%20%26%26%20DAY%28%3Fdate%29%20%3D%20%3FnowDay%29%0A%20%20%20%20OPTIONAL%20%7B%20%3Fperson%20wdt%3AP18%20%3FpersonImage%20%7D%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22.%20%7D%0A%0A%7D%0AORDER%20BY%20%3Fyear%0ALIMIT%20100" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" >
  </iframe>
</figure>

[Return to Experiments page]({{ '/experiments' | absolute_url }})

# Lab Report

## EXPERIMENT LABEL/TITLE
Map: Whose birthday is today?

## TL;DR
See which composers and performers from Carnegie Hall’s performance history were born on this day by plotting them on a map.

## -verbose
The scope is limited to those people for whom we have birthdate and birthplace information.

## METHODS
We created a SPARQL query using Wikidata’s query service. Since composer/performer identifiers from Carnegie Hall’s linked open dataset have their own official Wikidata property, Carnegie Hall Agent ID (P4104), which have been mapped to just over 14,000 Wikidata items, we can query Wikidata for birth locations of these people, binding today’s day and month for that part of each person’s birthdate:

```
#defaultView:Map
SELECT ?person ?personLabel ?personImage ?birthPlaceLabel ?location (YEAR(?date) as ?year)
(IRI(CONCAT("http://data.carnegiehall.org/names/",(STR(?chAgent_id)))) AS ?chLOD)
WHERE
{
    BIND(MONTH(NOW()) AS ?nowMonth)
    BIND(DAY(NOW()) AS ?nowDay)

    ?person wdt:P569 ?date ;
            wdt:P19 ?birthPlace ;
            wdt:P4104 ?chAgent_id .
    ?birthPlace wdt:P625 ?location .
    FILTER (MONTH(?date) = ?nowMonth && DAY(?date) = ?nowDay)
    OPTIONAL { ?person wdt:P18 ?personImage }
    SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }

}
ORDER BY ?year
LIMIT 100
```

We used the default map template available on Wikidata’s query service to create the map. You can view (and edit) the query by hovering your mouse over the far-right side of the map; from the pop-up menu that appears, click on “Edit SPARQL”.

## CONCLUSIONS
### what we learned
Wikidata’s out-of-the-box display templates are a wonderful way to easily create data visualizations, and do not require hosting your own dataset or creating your own visualization tools. They allow us to leverage the Carnegie Hall Agent ID property to surface interesting connections between CH’s named entities and external data/resources.


[Another version of this map query]({{ '/experiments/chdl-0001-b' | absolute_url }}) included a link back to an HTML version of Carnegie Hall’s performance history (the <a href="https://www.carnegiehall.org/About/History/Performance-History-Search" target="_blank">Performance History Search</a> on the Carnegie Hall website) in order to provide an easily human-readable version of each person’s history at the hall. The HTML version launched in 2013, well prior to our release of the same data as RDF in 2017; although the source database is the same, the process that translates the data for display is a bit different and was developed separately. This creates a few challenges when attempting to create links to PHS search filters:
- Our source database for CH’s performance history data, a proprietary SQL-based product designed for concert planning, stores performers and composers in separate tables. When the data is surfaced in the HTML Performance History Search (PHS), that separation between composers and performers remains. Query filters are constructed from a search index based on the name string of the composer or performer.
o	Our RDF version of the data solves this problem of (potential) dual IDs by creating a single ID for each named entity, with statements defining their role according to associations with creative works (as a composer, arranger, lyricist, etc.) and/or events (as a performer).
- In order to construct the PHS link, a URL-safe version of the Wikidata item label (i.e. the name of the composer or performer, with URL-encoded characters replacing spaces and other reserved characters) must be concatenated with a base URL, e.g. <a href="https://www.carnegiehall.org/About/History/Performance-History-Search?q=&dex=prod_PHS&pf=Juan%20Tizol" target="_blank">```https://www.carnegiehall.org/About/History/Performance-History-Search?q=&dex=prod_PHS&pf=Juan%20Tizol```</a>.

### further investigation 
- Initial attempts at creating the PHS link using the Wikidata Label Service failed, since (we believe) the label service is the last part of the query to be executed, which meant the labels were not available to be added when the BIND clause is running.
- In order get Item labels without using the SERVICE wikibase:label, you need to ask for the label explicitly in the WHERE part of the SELECT clause, e.g. ?person rdfs:label ?name filter (lang(?name) = "en"). While this then makes the label available to concatenate with a PHS filter URL and BIND to a variable, it significantly slows the query.
- If Wikidata’s item label happens to be different from Carnegie Hall’s (e.g. the Wikidata label includes a full middle name, where CH’s includes only a middle initial), the performance history search link will return zero results.
- In the source database, additional creators for works (e.g. co-composers, arrangers, lyricists, etc.) are stored in a separate (linked) table for each work. When the PHS was created in 2013, these were considered out-of-scope, and are not surfaced; so, although these names (and their relationship to any creative works) are part of the RDF dataset, any PHS links created using them return no results.

[Return to Experiments page]({{ '/experiments' | absolute_url }})
