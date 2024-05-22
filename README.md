# Oslofjord-init

## Installation

1.  Make sure that Docker engine or Docker desktop are installed.  The command `docker -v` should print out a version number.
2. Clone the startup-repo (this repository): `git clone --recurse-submodules git@github.com:oslofjord-twin/Oslofjord-init.git`.
3. Navigate into the folder: `cd Oslofjord-init`.
4. Clone the repo containing some test-data: `git clone git@github.com:oslofjord-twin/Oslofjord-data.git`
5. Run `python3 OslofjordDB-API/db/scripts/dataToCsv_init.py`
6. Run `python3 OslofjordDB-API/db/scripts/dataToSQL.py`


## Start the twin

To start the twin, start the docker containers with the command `docker compose up -d`.

After a while, the application will be be available by opening the address `http://localhost:3000` in a browser.


## Start the runtime-monitoring:

Follow the steps in the readme here: https://github.com/oslofjord-twin/OslofjordRV

## Simulation
To fill the database with simulation data:
1. Enter the shell of the hydrodrift-container:
```
docker exec -it hydrodrift bash
```

2. Navigate into the Hydrodrift folder
```
cd Hydrodrift
```

3. Run the model for date of interest </br>
Note: the chosen date requires available sensor data in the database

```
python main.py "year" "month" "day"
```

or

```
python main.py "year" "month" "day" "hour"
```
</br>

For the data in the Oslofjord-data repository, use:
```
python main.py 2024 4 14
python main.py 2024 4 15
```

Read more here: https://github.com/oslofjord-twin/OslofjordSM

## Updating the code

To get the latest version, run `git pull --recurse-submodules`.

To update the submodule sources to the latest upstream version, run the following command: `git submodule update --remote --merge`, commit and push the resulting changes.

To run after changing source code, use this command: `docker compose up --build`
