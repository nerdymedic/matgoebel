# Instruction for update_publications.sh

To run:
sh update_pubs.sh

## Explanation
The academic-cli-import (https://github.com/GetRD/academic-file-converter) relies on Python. It wants SSL to work. SSL for the system version of Python on Mac breaks this. The solution is to use pipx (create a virtual environment for the academic application and forces it to use the correct library).

## Force the downgrade
pipx runpip academic install urllib3==1.26.20

## Check version
source /Users/mat/.local/pipx/venvs/academic/bin/activate
pip3 show urllib3

If the output shows the correct version (1.26.20 rather than 2.x) we're good to go! However we have to make sure we run academic from within the environment.

## Running it
source /Users/mat/.local/pipx/venvs/academic/bin/activate
cd ~/Desktop 
academic import publications.bib publication/ --compact

## A note about Zotero
Go to "My Publications" on the left
Select all (cmd+A)
Right-click, Export Items
Format: BibTeX
Save to Desktop (publications.bib)