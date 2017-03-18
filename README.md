# 45brains
This repository holds the data for the 45brains.online website.

# Data
The `/data` directory currently holds all information we know about the 45 brains in machine readable form. 

Due to their already proven unlimited power, we can only assume that the 45 brains will monitor our progress through the 
very means we are using to expose them.

## `brains.json`
This file holds all the information we know about the brains. 

It contains an array of JSON objects with the following keys:

- id (int): Integer used to identify brain.
    - **mandatory**
- name (string): Name brain calls itself.
    - **mandatory**
- bio (string): Biography of brain.
    - **mandatory**
- images (array<string>): Array of image urls for brain
    - **mandatory**
    - If url is in format `media@<picture.png>` it is assumed that it is identifying an image in the path: `/media/brains/<brain.id>/<picture.png>`.
- status (enum): Status of brain in 45brains project
    - **mandatory**
    - Must have one of the following values:
        - `confirmed`: Brain is a confirmed an Actual Human Brain by an Idle Thumbs team member
        - `partial`: Brain holds partial cannon status in Idle Thumbs universe
        - `proposed`: Brain has been proposed to Idle Thumbs network team as an Actual Human Brain
        - `tbd`: Brain has yet to be confirmed
- messages (array<string>): Array of message objects from the brain
    - **mandatory**
    - Each object in array must be in the format:
        - quote (string): Exact text transcription of brain's message
        - notes (array<string>): Array of notes represented as strings
       - medium (string): Medium in which message was delivered by brain
- discovered_on (uri): Where the brain was discovered
    - Must be a all lowercase uri in format: `show:episode`
        - show (string): Name of show which brain was discovered on
            - If show is more than one word just remove spaces
        - episode (string): Episode number or id which brain was discovered on
            - `-1` if unknown
    - ex: `importantiftrue:4` for Important If True episode 4.
- links (array<object>): Array of link objects for brain
    - Each object in array must be in format:
        - text (string): Text to show for link
        - link (string): Link URL
