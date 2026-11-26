# MAPv5

Research institutions map with author profiles and a ranking.

## Files

| File | What it is |
| --- | --- |
| `index.html`, `app.js` | The map |
| `authors.html`, `authors.js` | Author profiles |
| `ranking.html`, `ranking.js` | Author ranking |
| `style.css` | Styling for all pages |
| `map_data.json`, `papers.json`, `authors.json` | Data the pages load (made by `build_data.py`) |
| `build_data.py` | Turns the CSV files into the three JSON files |
| `extra_coordinates.csv` | Coordinates from MAPv4 for 35 institutions that have none in `institutions_located.csv` |

## Updating the data

Put the CSV files (`DOIVenueTitleYearAuthors.csv`, `institutions_located.csv`,
`authors_merged.csv`, `PeopleToBeRanked.csv`, `top_collaborators.csv`) next to
`build_data.py` and run `python build_data.py`. It rewrites the three JSON files.

The CSV files don't need to be in the repository. `authors_merged.csv` contains
email addresses, so keep it out of a public repository. The JSON files only
say whether an email is known.

Authors with more than one ORCID iD: `build_data.py` asks ORCID's public site
which iD has a real profile with the author's name and keeps only that one.
This needs an internet connection and takes about a minute. When it can't
tell, the profile lists every iD as ORCID 1, ORCID 2, ... The website itself
never contacts ORCID.
