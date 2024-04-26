# Oslofjord-setup-script

## Prerequisites: 
- Docker engine or Docker desktop
- npm

## Clone and start the Dockerized parts:
1. Clone the startup-repo: `git clone git@github.com:oslofjord-twin/Oslofjord-setup-script.git`.
2. Navigate into the folder: `cd Oslofjord-setup-script`.
3. Clone the repo containing some test-data: `git clone git@github.com:oslofjord-twin/Oslofjord-data.git`
4. Initialize the git submodules: `git submodule init`.
5. Download the git submodules: `git submodule update`.
6. `python3 OslofjordDB/db/scripts/dataToCsv_init.py`
7. `python3 OslofjordDB/db/scripts/dataToSQL.py`

7. Start the docker containers: `docker compose up -d`.

## Start the runtime-monitoring:
1. Follow the steps in the readme here: https://github.com/oslofjord-twin/OslofjordRV

## Simulation
TODO: Does the simulation-part need to run something that is not started in the docker-compose?

## Start the front-end:
1. Navigate into the front-end repo to start the node.js-development server: `cd OslofjordFE/oslofjord-app`.
2. Build the project with `npm install` and run the front-end server: `npm run dev`.
3. The applciation will now be available at `http://localhost:3000`.
