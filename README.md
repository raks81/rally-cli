# rally-cli


## Intro
  * Provides a basic CLI based on Node.js
  * Not a full fledged client by any means
  * Does basic things like view iteration tasks, updating task todos, estimates and actuals
  * Works with multiple projects simultaneously
  * This is how the interface looks like:
![](https://raw.githubusercontent.com/raks81/rally-cli/master/images/ss.png)

## Usage
  * Install npm globally `npm install rally-cli -g`
  * Launch the help options from CLI:

```
bash-4.3$ rly help
Refer README.md of the project and update /usr/local/lib/node_modules/rally-cli/config/default.json file for initial configuration

Usage: rly [ <command> ] [<args>]

Minimal CLI for rally

Available commands:
  it | iteration # View and change current iteration
  t  | task      # View and edit tasks
  o  | open      # Open rally in browser
  d  | holidays  # View the configured holidays

```
  * Update the config as explained below

```
{
  "apiKey": "",  // API keys can be created/managed here: https://rally1.rallydev.com/login/accounts/index.html#/keys
  "projects": [
    {
      "name": "name of the project 1 (need not match the name in Rally)",
      "id": "/project/47117491111",  //Available in rally URL: https://rally1.rallydev.com/#/47117499999ud/iterationstatus
      "currentItr": "PI 2 - Iteration IP" //Name of the Iteration (should match Rally)
    },
    {
      "name": "name of the project 2 (need not match the name in Rally)",
      "id": "/project/47349901112",
      "currentItr": "PI 2 - Iteration IP"
    }
  ],
  "user": "",  //Your email id
  "uiLaunchCommand": "open -a Firefox https://rally1.rallydev.com/#/47117491111ud/custom/47826051111", //OS command to run to launch Rally in browser
  "rallySearchCommand": "open -a Firefox https://rally1.rallydev.com/#/47117491111ud/search?keywords=${keyword}",  //OS command to search in Rally in browser
  "holidays": [
    "08 Apr 2016",
    "14 Apr 2016"
  ]
}

```