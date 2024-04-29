# Oslofjord-setup-script

## Installation

1.  Make sure that Docker engine or Docker desktop are installed.  The command `docker -v` should print out a version number.
2. Clone the startup-repo (this repository): `git clone --recurse-submodules git@github.com:oslofjord-twin/Oslofjord-setup-script.git`.
3. Navigate into the folder: `cd Oslofjord-setup-script`.
4. Clone the repo containing some test-data: `git clone git@github.com:oslofjord-twin/Oslofjord-data.git`
5. Run `python3 OslofjordDB/db/scripts/dataToCsv_init.py`
6. Run `python3 OslofjordDB/db/scripts/dataToSQL.py`


## Start the twin

To start the twin, start the docker containers with the command `docker compose up -d`.

After a while, the application will be be available by opening the address `http://localhost:3000` in a browser.


## Start the runtime-monitoring:

Follow the steps in the readme here: https://github.com/oslofjord-twin/OslofjordRV

## Simulation

TODO: Does the simulation-part need to run something that is not started in the docker-compose?

## Updating the code

To get the latest version, run `git pull --recurse-submodules`.

To update the submodule sources to the latest upstream version, run the following command: `git submodule update --remote --merge`, commit and push the resulting changes.
