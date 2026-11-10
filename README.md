# medieval-churches
## Metadata Dataset of Medieval Churches from Central Europe

<!--->
[![version](https://img.shields.io/badge/version-1.0-orange)](#)
[![license](https://img.shields.io/badge/license-CC--BY--4.0-brightgreen)](https://creativecommons.org/licenses/by/4.0/)
[![date](https://img.shields.io/badge/date-2026--11--10-green)](#)
[![doi](https://img.shields.io/badge/DOI-xx.yyyy/zenodo.zzzzzz-blue)](https://doi.org/xx.yyyy/zenodo.zzzzzz)
<!--->

**Authors:**   
*[Hassenbach, Jona Marie](https://orcid.org/0009-0003-9200-2512) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0009-0003-9200-2512);*
*[Lantzberg, Melissa Sheena](https://orcid.org/0009-0002-3609-7695) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0009-0002-3609-7695);*
*[Eichert, Stefan](https://orcid.org/0000-0002-5827-0797) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0000-0002-5827-0797);*
*[Koschiček-Krombholz, Bernhard](https://orcid.org/0000-0001-7608-7446) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0000-0001-7608-7446);*
*[Adrian, Lisa](https://orcid.org/0000-0001-5176-8421) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0000-0001-5176-8421);*
*[Grünbacher, Elias](https://orcid.org/0009-0008-5264-3944) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0009-0008-5264-3944);*
*[Richards, Nina](https://orcid.org/0000-0002-4911-8451) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0000-0002-4911-8451);*
*[Vargha, Mária](https://orcid.org/0000-0002-6806-7434) [![orcID](/assets/ORCID-iD_icon-vector.svg)](https://orcid.org/0000-0002-6806-7434);*

## Funding
This research was funded in whole or in part by the Austrian Science
Fund (FWF) [10.55776/I6428](https://doi.org/10.55776/I6428). 

The research has also been funded in part by the
European Union (ERC-StG, RELIC, 101115501). Views and opinions expressed
are, however, those of the author(s) only and do not necessarily reflect
those of the European Union or the European Research Council. Neither
the European Union nor the granting authority can be held responsible
for them.

## Summary
This repository contains two final datasets of medieval churches from Central Europe for a study of church orientations, astronomical sunrise dates, and associated saints. The original church records were pulled from the THANADOS database.

## Files

| File | Records | Description |
|---|---:|---|
| `data/final_dataset.csv` | 1,341 | Church chronology, geometry, orientation, horizon measurements, sunrise dates, and associated saints. |
| `data/final_saints.csv` | 513 | Saints and their feast entries. A saint may appear in multiple rows. |

## Data dictionary

Both files are UTF-8 CSVs with a header row. Use a CSV reader to preserve quoted fields and values containing commas.

### `final_dataset.csv`

Geometry values are Well-Known Text (WKT) in EPSG:32633. Date lists are JSON arrays stored in CSV cells.

| Column | Description |
|---|---|
| `Thanados ID` | Church record identifier in THANADOS. |
| `Name` | Church name. |
| `Earliest begin YYYY` | Earliest beginning year recorded for the church. |
| `Latest begin YYYY` | Latest beginning year recorded for the church. |
| `Point (WKT)` | Centroid of the church polygon. |
| `Polygon (WKT)` | Church polygon geometry. |
| `Saints IDs` | IDs of saints associated with the church. |
| `Saints Text` | Names of the associated saints. |
| `Axis (WKT)` | Church-axis line geometry. |
| `East Point (WKT)` | Eastern point on the church axis. |
| `Azimuth (360°)` | Church-axis azimuth, in degrees. |
| `Horizon Point (WKT)` | Horizon point in the church's azimuth. |
| `Distance East-Point Horizon Point (m)` | Distance from the east point to the horizon point, in metres. |
| `Inclination (360°)` | Horizon inclination, in degrees. |
| `Horizon Elevation Difference (m)` | Absolute elevation difference between the horizon and observer point, in metres. |
| `Astronomical Sunrise days` | Sunrise dates matching the church's azimuth and horizon criteria, as `MM-DD` values. |
| `Astronomical Sunrise days mirrored` | Corresponding sunrise dates mirrored around June 21. |
| `Julian Calendar conversion` | Matched sunrise dates converted to the Julian calendar for the earliest beginning year. |
| `Julian Calendar conversion mirrored` | Mirrored sunrise dates converted to the Julian calendar for the earliest beginning year. |
| `human_annotated` | Indicates whether the data comes from the human-annotated dataset. For 821 of the churches the azimuth was manually verified and corrected if necessary. |

### `final_saints.csv`

Each row records a saint feast entry. 

| Column | Description |
|---|---|
| `Saints ID` | Saint identifier. |
| `Name` | Saint name. |
| `Wikidata ID` | Wikidata identifier, when available. |
| `Type` | Type of feast entry, as recorded in the file. |
| `Date` | Feast date associated with the entry. |
| `Place` | Place associated with the entry. `everywhere` means it is not location-specific. |

## License
This dataset is licensed under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://github.com/thanados-network/medieval-churches/blob/develop/LICENSE) license.
