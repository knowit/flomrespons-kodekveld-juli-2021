# Flomrespons kodekveld - juli 2021

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/knowit/flomrespons-kodekveld-juli-2021/blob/master/sample.ipynb)

## Data
Hydrometeorologisk data hentet fra Noregs vassdrags- og energidirektorat (NVE) og Meteorologisk institutt (MET). Datasettet inneholder vannstand- og vannføringsmålinger, observert vær, og historiske værprognoser, ved tre NVE-målestasjoner i uregulerte vassdrag: **Akslen**, **Brustuen** og **Nedre Sjodalsvatn**.  

Last ned: [hydmet-dataset.zip](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset.zip)

### Filstruktur
S3 root url: https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/
* hydmet-dataset/
    * [`station_data.json`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/station_data.json)
    * Akslen/
        * [`forecastedWeather.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Akslen/forecastedWeather.csv)
        * [`observedWeather.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Akslen/observedWeather.csv)
        * [`waterDischarge.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Akslen/waterDischarge.csv)
        * [`waterLevel.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Akslen/waterLevel.csv)
    * Brustuen/
        * [`forecastedWeather.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Brustuen/forecastedWeather.csv)
        * [`observedWeather.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Brustuen/observedWeather.csv)
        * [`waterDischarge.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Brustuen/waterDischarge.csv)
        * [`waterLevel.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Brustuen/waterLevel.csv)
    * Nedre Sjodalsvatn/
        * [`forecastedWeather.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Nedre+Sjodalsvatn/forecastedWeather.csv)
        * [`observedWeather.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Nedre+Sjodalsvatn/observedWeather.csv)
        * [`waterDischarge.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Nedre+Sjodalsvatn/waterDischarge.csv)
        * [`waterLevel.csv`](https://flomrespons-public-data.s3.eu-central-1.amazonaws.com/hydmet-dataset/Nedre+Sjodalsvatn/waterLevel.csv)
    
## Beskrivelser

### `forecastedWeather.csv`
Historiske værprognoser hentet fra [THREDDS](https://thredds.met.no/thredds/catalog.html) katalogen

| Felt | Enhet | Beskrivelse |
|------|-------| ----------- |
| reference_time  | Tidsstempel | Tidsstempel for utgangspunktet til prognosene |
| time | tidsstempel | Tidsstempel for når prognosen gjelder (fremtid fra reference_time) |
| air_temperature_2m  | Kelvin | lufttemperatur i kelvin |
| precipitation_amount  | mm/t | nedbød i millimeter sist time |
| wind_speed_10m  | m/s  |   |
| wind_direction_10m  | vinkelgrad |   |
| relative_humidity_2m  |   | luftfuktighet |
| air_pressure_at_sea_level  | Pascals |  Lufttrykk  |
| cloud_area_fraction  | Brøkdel |  Skydekke |
| met_run  |   | THREDDS kilde |

### `observedWeather.csv`
Beste antagelse om tidligere observert vær hentet fra [THREDDS](https://thredds.met.no/thredds/catalog.html) katalogen

| Felt | Enhet | Beskrivelse |
|------|-------| ----------- |
| reference_time  | Tidsstempel | Tidsstempel for observasjonen |
| time | tidsstempel | Tidsstempel for observasjonen (skal være lik reference_time) |
| air_temperature_2m  | Kelvin | lufttemperatur i kelvin |
| precipitation_amount  | mm/t | nedbød i millimeter sist time |
| wind_speed_10m  | m/s  |   |
| wind_direction_10m  | Vinkelgrad |   |
| relative_humidity_2m  |   | luftfuktighet |
| air_pressure_at_sea_level  | Pascals |  Lufttrykk  |
| cloud_area_fraction  | Brøkdel |  Skydekke |
| met_run  |   | THREDDS kilde |

### `waterDischarge.csv`
Vannføringsmålinger hentet fra [NVE HydAPI](https://hydapi.nve.no/UserDocumentation/)

| Felt | Enhet | Beskrivelse |
|------|-------| ----------- |
| time | tidsstempel |   |
| value | m^3/s  | kubikkmeter vann per sekund |
| correction |  | <ol start="0"><li>No changes</li><li>Manual- or ice correction</li><li>Interpolation</li><li>Value computed with models or/and other series</li></ol> |
| quality |  | <ol start="0"><li>Unknown</li><li>Uncontrolled</li><li>PrimaryControlled</li><li>SecondaryControlled</li></ol> |

### `waterLevel.csv`
Vannstandssmålinger hentet fra [NVE HydAPI](https://hydapi.nve.no/UserDocumentation/)

| Felt | Enhet | Beskrivelse |
|------|-------| ----------- |
| time | tidsstempel |   |
| value | m  | vannstand i meter over havet |
| correction |  | <ol start="0"><li>No changes</li><li>Manual- or ice correction</li><li>Interpolation</li><li>Value computed with models or/and other series</li></ol> |
| quality |  | <ol start="0"><li>Unknown</li><li>Uncontrolled</li><li>PrimaryControlled</li><li>SecondaryControlled</li></ol> |

## Lisenser
Norsk lisens for offentlige data (NLOD) https://data.norge.no/nlod/no/
