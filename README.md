# transferSkinCluster
This plug-in for Maya exports the skin cluster weights of your selected mesh to a file, which can then be used to re-create the skinning of the model.

Exporting and importing of skin weights is an important step during the rigging process in case a character needs to be rebuild.

There are many other solutions for this process and they all differ in style and speed, whereas speed is the most important difference, especially with meshes of higher resolution.

## Installation
Installation is easy with the included installer. See installationGuide.html for more details.

## MEL Commands
`// Writes the skin cluster of the selected mesh to a file.
icTransferSkinCluster 0 0`

`// Opens a window to let you select the skin cluster weights to import.
icTransferSkinCluster 1 0`

`// Get a list of extraction commands for use in custom scripts.
transferSkinCluster -h`

## Usage
**Export**
Select your skinned mesh and execute the export command.
After a successful export the export path is written to the script editor output.
The weight file is stored in the data folder of the current project as a regular text file with a custom extension (.scw).

**Import**
After executing the import command a window will list all stored skin weights in the data folder of the current project.
Select the data set and click the import button. The weights file contains the name of the bound geometry and the influencing joints, so it is not necessary to select anything.

When selecting a weights file and the node names stored in the file do not match the content of the current scene a second list will show all the unmatched names from the file.
The window will also display various renaming options:

- rename existing nodes in the scene by applying the selected node name from the list to the selected node in the scene
- use a search and replace to rename the file content according to the existing scene nodes; this creates a new weights file with modified names which can then be used for import
- add a prefix or suffix to rename the file content according to the existing scene nodes; this creates a new weights file with modified names which can then be used for import

For more information about the renaming options go to **Menu > Help > Rename Help** of the import window.
