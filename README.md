#
<p align="center">
<h1 align="center">Pilot and Heats Import Plugin for RotorHazard</h1>
<h3 align="center">This plugin allows you to import pilots and generate heats from a local file in RotorHazard.<br>
<a href="./README_CN.md">[🇨🇳中文]</a><br>
</h3>

## Features

- Import pilots from a local file
- Automatically create a race class
- Generate heats based on the imported data
- Assign pilots to appropriate heats

## Installation

- ### Manually

1. Clone this repository or download the source code.
2. Place the `pilot_local_importer` folder in your RotorHazard plugins directory `~/RotorHazard/src/server/plugins`.
3. Install dependancy `pip install openpyxl`
3. Restart your RotorHazard server.

- ### Commandline

```bash
cd ~
sudo rm -r RotorHazard/src/server/plugins/pilot_local_importer
wget https://github.com/l1cardo/RH-Pilot-Local-Importer/releases/latest/download/pilot_local_importer.zip
unzip pilot_local_importer.zip -d pilot_local_importer
cp -r pilot_local_importer RotorHazard/src/server/plugins/
rm -r pilot_local_importer
rm pilot_local_importer.zip
pip install openpyxl
sudo systemctl restart rotorhazard.service
```

## Usage

1. Create an Excel file that **MUST** follow the format below:

- Or You can dowload a template file [here](https://github.com/L1cardo/RH-Pilot-Local-Importer/raw/refs/heads/main/asset/template.xlsx)

![](/asset/sheet.png)

- `Class Name`: Any Class Name you want, can not be the same as existed ones

- `Heat`: Heat name, Pilots that have the same Heat name will be placed in the same Heat

- `Pilot`: Pilot name

- `Callsign`: Callsign **MUST** be unique

- `Team`: The team where the pilot at, **ONLY** supports the single letters of `A`-`Z` and **MUST** be uppercase

- `Frequency`: RH can not set the Frequency using plugin, this is just for convenient purpose

- `Color`: Support following colors and any Hex color code, `Blue, Orange, Green, Red, Yellow, Purple, Cyan, Grey, Any Hex color code #7f679`

2. Navigate to the "Data Management" panel in the Format page.

3. Choose `Import Pilots and Heats` for Importer, and select your Excel file 

4. Click the "Import" button to start the import process.

## License

[MIT](LICENSE)