# Pilot and Heats Import Plugin for RotorHazard

This plugin allows you to import pilots and generate heats from a local file in RotorHazard.

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

![](sheet.png)

- `Class Name`: Any Class Name you want, can not be the same as existed ones

- `Heat`: Heat name, Pilots in the same heat MUST have the same Heat name

- `Pilot`: Pilot name, Callsign will also use Pilot name

- `Frequency`: RH can not set the Frequency using plugin, this is just for convenient purpose

- `Color`: Support following colors and any Hex color code, `Blue, Orange, Green, Red, Yellow, Purple, Cyan, Grey, Any Hex color code #7f679`

2. Navigate to the "Data Management" panel in the Format page.

3. Choose `Import Pilots and Heats` for Importer, and select your file 

4. Click the "Import" button to start the import process.

## License

[MIT](LICENSE)