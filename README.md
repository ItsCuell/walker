# RLPL Transports

### Create a branch for the Transport(s) you wish to add.

#### Transport Structure: 
`source`, `destination`, `requirements`, `type`

`source` & `destination` = 
`x`, `y`, `plane`


**Accepted Requirements:**

itemRequirements[]:
- ids
- amount
- location (INVENTORY/ EQUIPMENT)
- reduction (AND/OR)

skillRequirements[]:
- skill
- level

varRequirements[]:
- comparison (LESS_THAN/LESS_THAN_EQUAL/GREATER_THAN/GREATER_THAN_EQUAL/EQUAL)
- type (VARBIT/VARP)
- var
- value

questRequirements[]:
- quest
- states[] (IN_PROGRESS/NOT_STARTED/FINISHED)

miscRequirements[]:
- member (true/false)

**Accepted types:** 
`OBJECT`,
`NPC`,
`ITEM_USE`,
`SLASH_WEB`,
`DIG`

type `data`:
- id (int)
- name (string)
- action (string)
- dialog[] (string)

Example `OBJECT` transport:
```
{
    "source": {
      "x": 1799,
      "y": 9506,
      "plane": 0
    },
    "destination": {
      "x": 1795,
      "y": 3106,
      "plane": 0
    },
    "requirements": {
      "miscRequirements": {
        "member": true
      }
    },
    "type": "OBJECT",
    "data": {
      "id": 50750,
      "action": "Exit"
    }
  }
```
Example `NPC` transport:
```
{
    "source": {
      "x": 2954,
      "y": 3147,
      "plane": 0
    },
    "destination": {
      "x": 3032,
      "y": 3217,
      "plane": 1
    },
    "requirements": {
      "itemRequirements": [
        {
          "ids": [
            995
          ],
          "amount": 30,
          "location": "INVENTORY",
          "reduction": "AND"
        }
      ],
      "questRequirements": [
        {
          "quest": "PIRATES_TREASURE",
          "states": [
            "FINISHED"
          ]
        }
      ],
      "miscRequirements": {
        "member": false
      }
    },
    "type": "NPC",
    "data": {
      "id": 3648,
      "action": "Pay-Fare"
    }
  }
```
There are many more examples in the transports file.

#### <ins>Update / Testing:<ins>
Edit the rlplTransports.json file that's in the `.ThePlugRLPL` folder and reload to see if they're valid, please test them locally first before committing.

When commiting make sure to update the "transports_version" in the walker_info.json file to force the client to download the newer version.

## **Ensure you add both directions!**
