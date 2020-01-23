# chdl-0001

## Whose birthday is today?

A birthplace map of performers and composers from Carnegie Hall's performance history. 

Be patient! Takes a few seconds to load.

<figure class="map_container">
  <iframe 
  style="width: 80vw; height: 50vh; border: none;" src="https://query.wikidata.org/embed.html#%23defaultView%3AMap%0ASELECT%20%3Fperson%20%3Fname%20%3FpersonImage%20%3FbirthPlaceLabel%20%3Flocation%20%3FphsLink%20%28YEAR%28%3Fdate%29%20as%20%3Fyear%29%0A%28IRI%28CONCAT%28%22http%3A%2F%2Fdata.carnegiehall.org%2Fnames%2F%22%2C%28STR%28%3FchAgent_id%29%29%29%29%20AS%20%3FchLOD%29%0AWHERE%0A%7B%0A%20%20%20%20BIND%28MONTH%28NOW%28%29%29%20AS%20%3FnowMonth%29%0A%20%20%20%20BIND%28DAY%28NOW%28%29%29%20AS%20%3FnowDay%29%0A%0A%20%20%20%20%3Fperson%20wdt%3AP569%20%3Fdate%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP19%20%3FbirthPlace%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20wdt%3AP4104%20%3FchAgent_id%20%3B%0A%20%20%20%20%20%20%20%20%20%20%20%20rdfs%3Alabel%20%3Fname%20filter%20%28lang%28%3Fname%29%20%3D%20%22en%22%29.%0A%20%20%20%20%3FbirthPlace%20wdt%3AP625%20%3Flocation%20.%0A%20%20%20%20FILTER%20%28MONTH%28%3Fdate%29%20%3D%20%3FnowMonth%20%26%26%20DAY%28%3Fdate%29%20%3D%20%3FnowDay%29%0A%20%20%20%20OPTIONAL%20%7B%20%3Fperson%20wdt%3AP18%20%3FpersonImage%20%7D%0A%20%20%20%20BIND%28%0A%20%20%20%20%20%20IF%28xsd%3Ainteger%28%3FchAgent_id%29%20%3C%201000000%2C%20IRI%28CONCAT%28%22https%3A%2F%2Fwww.carnegiehall.org%2FAbout%2FHistory%2FPerformance-History-Search%3Fq%3D%26dex%3Dprod_PHS%26pf%3D%22%2C%20%28STR%28ENCODE_FOR_URI%28%3Fname%29%29%29%29%29%2C%0A%20%20%20%20%20%20%20%20%20%20%20%20%20IRI%28CONCAT%28%22https%3A%2F%2Fwww.carnegiehall.org%2FAbout%2FHistory%2FPerformance-History-Search%3Fq%3D%26dex%3Dprod_PHS%26cmp%3D%22%2C%20%28STR%28ENCODE_FOR_URI%28%3Fname%29%29%29%29%29%29%0A%20%20%20%20%20%20%20%20%20AS%20%3FphsLink%29%20.%0A%20%20%20%20SERVICE%20wikibase%3Alabel%20%7B%20bd%3AserviceParam%20wikibase%3Alanguage%20%22en%22.%20%7D%0A%0A%7D%0AORDER%20BY%20%3Fyear%0ALIMIT%20100" referrerpolicy="origin" sandbox="allow-scripts allow-same-origin allow-popups" >
  </iframe>
</figure>

[Return to Experiments page]({{ '/experiments' | absolute_url }})
