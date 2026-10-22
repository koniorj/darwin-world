# Darwin World

Simulation of animal evolution on a map, built with Java and JavaFX user interface. Animals move across the board, forage for grass, reproduce, and pass down their genes (with small mutations). You can observe population dynamics over time and analyze which evolutionary strategies survive.

Project developed for the Object-Oriented Programming course (AGH University of Technology, Computer Science).

## Authors
- Paweł Pochwalski
- Justyna Konior

## Video Presentation
Short video demonstrating the application in action:

https://github.com/user-attachments/assets/303ab0a5-631a-4d8a-bb95-317e23c03dc4



# How the Simulation Works
The world consists of a cylindrical map: the left and right edges wrap around, while the top and bottom form boundaries (walls). The central strip of the map represents a jungle where grass grows more frequently; the remaining areas are steppes.

Each simulation day follows this sequence:
1. Animals lose energy (daily cost of living).
2. Animals move according to their genome.
3. Animals standing on grass consume it and regain energy.
4. Animals with sufficient energy reproduce. The offspring receives a combination of the parents' genes, with a chance for random mutations.
5. New grass spawns on the map.
6. Dead animals are removed from the board, but their lifespans are included in the overall statistics.

## Modes
* **Normal:** Constant environmental conditions throughout the simulation.
* **Seasonal:** Alternating summer and winter seasons. During winter, temperatures drop, increasing the daily energy cost of living for animals. Season duration, minimum temperature, and heat distribution radius are fully configurable.


## Features
* Configure all simulation parameters (map size, initial count of animals and grass, energy values, reproduction costs, genome length, mutation ranges, and more).
* Use ready-made presets (*Sterile*, *India*, *Postapo*).
* Save and load configuration settings from `.txt` files.
* Run multiple simulations simultaneously, each in its own window.
* Pause and resume the simulation at any time.
* Monitor real-time statistics: animal and grass counts, empty tiles, dominant genotype, average energy, average lifespan, and average number of children.
* View dynamic line charts tracking statistics over time (including temperature in seasonal mode).
* Click on an animal while paused to track its genome, energy, age, child count, descendant count, and consumed plants.
* Export daily statistics to a CSV file.


## Getting Started

### Prerequisites
JDK 25 is required (Gradle will attempt to fetch it automatically if missing). Dependencies, including JavaFX and OpenCSV, are downloaded automatically.

```bash
git clone https://github.com/Calgune/Darwin-World.git
cd Darwin-World/oolab
./gradlew run
```

> **Note for Windows users:** Use `gradlew.bat` instead of `./gradlew`.

Alternatively, open the project in IntelliJ IDEA, wait for Gradle sync to complete, and run the `application > run` task.

*If IntelliJ fails to launch the application using the run button, go to `Settings > Build, Execution, Deployment > Build Tools > Gradle` and set **Build and run using** to **Gradle**.*


## Technologies
* Java 25
* JavaFX 25
* Gradle
* OpenCSV
* JUnit 5


## Project Structure
The source code is organized into packages under `agh.ics.oop`:

* `model` – Animals, grass, genomes, map logic, and configurations.
* `model.maps` – Map implementations.
* `model.simulation` – Core simulation engine and logic (normal and seasonal modes).
* `model.observers` – Observers monitoring map and statistic updates.
* `model.util` – Helper utilities (CSV export, configuration file handling, etc.).
* `presenter` – JavaFX view controllers.

UI views are defined in FXML files located in `src/main/resources`.
