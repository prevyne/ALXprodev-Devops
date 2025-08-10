Advanced shell scripting
 Novice
 Weight: 1
 Project will start Aug 4, 2025 12:00 AM, must end by Aug 11, 2025 12:00 AM
 Checker was released at Aug 4, 2025 12:00 AM
 Manual QA review must be done (request it when you are done with the project)
 An auto review will be launched at the deadline
Quiz questions
Great! You've completed the quiz successfully! Keep going! (Show quiz)
Tasks
0. API Request Automation
mandatory
Objective: Automate the process of making API requests to the Pokémon API and saving the results to a file

Instructions:

Write a shell script that makes a request to the Pokémon API and retrieves data for a specific Pokémon Pikachu.

It should save the response to a json file: data.json

If the request fails, it should log the error to an error file: errors.txt

Sample Output

ghostmode@GhostMode:~$ jq . < data.json | head -n 50
{
  "abilities": [
    {
      "ability": {
        "name": "static",
        "url": "https://pokeapi.co/api/v2/ability/9/"
      },
      "is_hidden": false,
      "slot": 1
    },
    {
      "ability": {
        "name": "lightning-rod",
        "url": "https://pokeapi.co/api/v2/ability/31/"
      },
      "is_hidden": true,
      "slot": 3
    }
  ],
  "base_experience": 112,
  "cries": {
    "latest": "https://raw.githubusercontent.com/PokeAPI/cries/main/cries/pokemon/latest/25.ogg",
    "legacy": "https://raw.githubusercontent.com/PokeAPI/cries/main/cries/pokemon/legacy/25.ogg"
  },
  "forms": [
    {
      "name": "pikachu",
      "url": "https://pokeapi.co/api/v2/pokemon-form/25/"
    }
  ],
  "game_indices": [
    {
      "game_index": 84,
      "version": {
        "name": "red",
        "url": "https://pokeapi.co/api/v2/version/1/"
      }
    },
    {
      "game_index": 84,
      "version": {
        "name": "blue",
        "url": "https://pokeapi.co/api/v2/version/2/"
      }
    },
    {
      "game_index": 84,
      "version": {
        "name": "yellow",
        "url": "https://pokeapi.co/api/v2/version/3/"
ghostmode@GhostMode:~$
Repo:

GitHub repository: ALXprodev-Devops
Directory: Advanced_shell
File: apiAutomation-0x00
1. Extract Pokémon Data
mandatory
Objective: Use advanced text manipulation tools (jq, awk, sed) to extract specific data from the API response.

Instructions:

Write a script that extracts the Pokémon’s name, height, weight, and type from the JSON file created in Task 0.

Format the output in a human-readable way,“Pikachu is of type Electric, weighs 6kg, and is 0.4m tall.”

You should only use these commands: jq, awk, sed

Sample Output:

ghostmode@GhostMode:~$ ./parse_pikachu
Pikachu is of type Electric, weighs 6kg, and is 0.4m tall.
ghostmode@GhostMode:~$
Repo:

GitHub repository: ALXprodev-Devops
Directory: Advanced_shell
File: data_extraction_automation-0x01
2. Batch Pokémon Data Retrieval
mandatory
Objective: Automate the retrieval of data for multiple Pokémon and store it in separate files.

Instructions:

Create a script that loops through a list of Pokémon [Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon]

For each Pokémon, retrieve its data from the API and save it to a separate file named after the Pokémon (e.g., pikachu.json, bulbasaur.json…).

Handle any potential rate-limiting issues by adding a delay between requests.

Sample Output:

ghostmode@GhostMode:~$ ./fetch_multiple_pokemon
Fetching data for bulbasaur...
Saved data to pokemon_data/bulbasaur.json ✅
Fetching data for ivysaur...
Saved data to pokemon_data/ivysaur.json ✅
Fetching data for venusaur...
Saved data to pokemon_data/venusaur.json ✅
Fetching data for charmander...
Saved data to pokemon_data/charmander.json ✅
Fetching data for charmeleon...
Saved data to pokemon_data/charmeleon.json ✅
ghostmode@GhostMode:~$ jq . < pokemon_data/bulbasaur.json | head -n 30
{
  "abilities": [
    {
      "ability": {
        "name": "overgrow",
        "url": "https://pokeapi.co/api/v2/ability/65/"
      },
      "is_hidden": false,
      "slot": 1
    },
    {
      "ability": {
        "name": "chlorophyll",
        "url": "https://pokeapi.co/api/v2/ability/34/"
      },
      "is_hidden": true,
      "slot": 3
    }
  ],
  "base_experience": 64,
  "cries": {
    "latest": "https://raw.githubusercontent.com/PokeAPI/cries/main/cries/pokemon/latest/1.ogg",
    "legacy": "https://raw.githubusercontent.com/PokeAPI/cries/main/cries/pokemon/legacy/1.ogg"
  },
  "forms": [
    {
      "name": "bulbasaur",
      "url": "https://pokeapi.co/api/v2/pokemon-form/1/"
    }
  ],
ghostmode@GhostMode:~$
Repo:

GitHub repository: ALXprodev-Devops
Directory: Advanced_shell
File: batchProcessing-0x02
3. Summarize Pokémon Data
mandatory
Objective: Create a report that summarizes data for multiple Pokémon.

Instructions:

Write a shell script that reads all the JSON files generated in Task 2 and extracts the name, height, and weight of each Pokémon.

Generate a CSV file containing the Pokémon’s name, height, and weight.

Use awk to calculate the average height and weight of all Pokémon in the report.

Sample Output:

ghostmode@GhostMode:~$ ./pokemon_report
CSV Report generated at: pokemon_report.csv

Name,Height (m),Weight (kg)
Bulbasaur,0.7,6.9
Charmander,0.6,8.5
Charmeleon,1.1,19.0
Ivysaur,1.0,13.0
Venusaur,2.0,100.0

Average Height: 1.08 m
Average Weight: 29.48 kg
ghostmode@GhostMode:~$
Repo:

GitHub repository: ALXprodev-Devops
Directory: Advanced_shell
File: summaryData-0x03
4. Error Handling and Retry Logic
mandatory
Objective: Add robust error handling and retry logic for API requests.

Instructions:

Modify the script from Task 2 to handle potential errors (e.g., network issues, invalid Pokémon names).

If an API request fails, implement a retry mechanism that attempts the request up to 3 times before logging the error and skipping to the next Pokémon.

Repo:

GitHub repository: ALXprodev-Devops
Directory: Advanced_shell
File: batchProcessing-0x02
5. Parallel Data Fetching
mandatory
Objective: Speed up data retrieval using parallel processing.

Instructions:

Write a script that fetches data for these Pokémon[Bulbasaur, Ivysaur, Venusaur, Charmander, Charmeleon ] in parallel by leveraging background processes and process management tools.

Ensure that the script handles background processes properly and waits for all processes to complete before moving to the next step.

Repo:

GitHub repository: ALXprodev-Devops
Directory: Advanced_shell
File: batchProcessing-0x04