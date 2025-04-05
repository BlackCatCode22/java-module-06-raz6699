# Module06 Activities: Design Document

# Zoo Animal Management System - Overview

This program simulates a zoo management system that reads information from input files, processes it to assign names, IDs, birth dates, and organize the zoo's population by species. The results are output to both a file and the console.

## Key Features:

### 1. **Animal Class:**
- The `Animal` class encapsulates key attributes of each animal, such as `name`, `id`, `species`, `gender`, `color`, `weight`, `birthDate`, and `origin`.
- The class constructor initializes these attributes, and the `toString()` method provides a formatted string for output, ensuring each animal’s details are presented clearly.

### 2. **File Input:**
- The program relies on two files:
    - **animalNames.txt**: Contains pre-defined lists of names for each species (e.g., hyenas, lions, tigers). Each species has a list of potential names that can be assigned to arriving animals.
    - **arrivingAnimals.txt**: Describes the arriving animals, including their age, gender, color, weight, birth season, and origin. This data is used to populate the attributes of each animal in the system.

### 3. **Name Assignment:**
- Names are assigned to animals randomly from the species-specific list provided in `animalNames.txt`. The program ensures that each animal gets a unique name by tracking the names already used for each species.
- If a name has already been assigned, it won’t be reused. The program shuffles the list of available names before each assignment to ensure randomness and uniqueness.
- If there are no available names left, the program will reset the used names for that species and shuffle the list again.

### 4. **Unique ID Generation:**
- Each animal is given a unique ID, which is derived from its species and a sequential number. For example, hyenas might have IDs like `Hy01`, `Hy02`, and so on.
- The program maintains a counter for each species to ensure IDs are assigned incrementally.

### 5. **Birth Date Calculation:**
- The birth date for each animal is calculated based on its age and the season of birth provided in the input data.
- For example, if an animal is 4 years old and born in the spring, its birth date would be set to March 21st of the year it was born, calculated from the current year minus its age.

### 6. **Output Generation:**
- After processing all the animals, the program generates a detailed report in the `zooPopulation.txt` file. This report lists all the animals in the zoo, grouped by species (e.g., Hyena Habitat, Lion Habitat, etc.).
- The program also prints the same information to the console, allowing real-time visualization of the zoo's population.

## Flow of the Program:

1. **Reading Input Files:** The program first reads `animalNames.txt` to build lists of available names for each species and `arrivingAnimals.txt` to get the attributes of each animal.
2. **Animal Object Creation:** For each arriving animal, an `Animal` object is created with the appropriate attributes, including a randomized name, unique ID, calculated birth date, and arrival date.
3. **Assigning Names and IDs:** The program assigns names from the species list, ensuring no duplicates, and generates unique IDs based on the species and count of animals processed.
4. **Storing and Organizing Animals:** Animals are grouped by species using a `Map` to organize the zoo population. Each species has its own section in the output report.
5. **Final Report:** The zoo’s full population is output to `zooPopulation.txt`, and also displayed on the console, showing a clear breakdown of animals in each habitat.

## Output Example:

For example, if there are hyenas, lions, tigers, and bears in the zoo, the output might look like this:


Hyena Habitat: Hy01; Shenzi; birth date: 2021-03-21; tan; Female; 70 pounds; from Friguia Park, Tunisia; arrived 2025-04-05 Hy02; Nne; birth date: 2013-09-21; brown; Male; 150 pounds; from Friguia Park, Tunisia; arrived 2025-04-05 ...

Lion Habitat: Li01; Simba; birth date: 2019-03-21; tan; Female; 300 pounds; from Zanzibar, Tanzania; arrived 2025-04-05 Li02; Mufasa; birth date: 2003-09-21; golden; Male; 450 pounds; from Zanzibar, Tanzania; arrived 2025-04-05 ...

etc.

This system helps organize a zoo’s population by tracking each animal's details, ensuring that the zoo’s records remain clear and up-to-date.
