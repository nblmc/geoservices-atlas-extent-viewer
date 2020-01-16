# Geoservices Atlas Extent Viewers
## Reference Maps for Use With Atlascope and Libguides

## index.html - for use with Atlascope

## libguides.html - for use with Libguides

### Steps for updating

1.  Open the *Urban Atlases Comprehensive* Airtable and select the *Libguide Layers* view. This view is filtered so that it excludes records with `json_status` set to `no index`, and it selects only the columns needed for this tool.

2. From Airtable, download a CSV of the *Libguide Layers* view.

3. Move the downloaded file to this repository and name it `atlases-data.csv`, replacing the former file.

4. Commit changes to this repository and push to GitHub.

5. SSH in to Geoservices, open this repository directory, and pull updates from GitHub.

### Steps for embedding into Libguide

1. The categories included in an entry's `geo_extent_discrete` column in Airtable are used to build specific Libguide indicator maps.

2. Test out a given category by opening `https://geoservices.leventhalmap.org/atlas-extent-viewer/libguides.html#{{GEOGRAPHIC_EXTENT}}` in a browser. The `{{GEOGRAPHIC_EXTENT}}` variable should be the exact text of a geographic extent value from the Airtable, with spaces replaced with hyphens and case sensitive. Examples: `https://geoservices.leventhalmap.org/atlas-extent-viewer/libguides.html#East-Boston`.

3. Geographic extent values can be created arbitrarily. For instance, if we added a `North End` flag to the `geo_extent_discrete` column in Airtable, then we could create an indicator map for all the Atlases flagged with `North End`. _Note: Do not include a comma in the name of any single geographic extent._

4. If the preview looks how you think it should, embed this into the Libguide page:   
```
<iframe src="https://geoservices.leventhalmap.org/atlas-extent-viewer/libguides.html#{{GEOGRAPHIC_EXTENT}}"></iframe>
```