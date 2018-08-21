# Heron Worlds

The *heron_worlds* package was created to simplify world creation for the Heron simulator. All that is required is a world name and a 3D file of the world's seabed, islands, coast, etc.

When making the 3D file, ensure that the sealevel is at Z = 0. Anything below this point is considered underwater, anything above this point is out of the water, etc.

## To create a world
With [WORLD_NAME] as your world's name and [WORLD_FILE] as the file path to your 3D file (an absolute file path), run the following command to create the world files:  
```rosrun heron_worlds make_world -n [WORLD_NAME] -m [WORLD_FILE]```

This will create the necessary files in the *heron_worlds* package to simulate your world! The command has a few options other than "n" and "m" but only those two are required.

##### Other options
- -a or --author: Author name  
- -e or --author_email: Author email  
- -d or --desc: World description
- -s or --world_size: World Size (m)

## To launch the world
With [WORLD_NAME] as your world's name, run one of the following commands to simulate your world:  
Without a Heron: ```roslaunch heron_worlds [WORLD_NAME].launch```  
With a Heron: ```roslaunch heron_gazebo heron_world.launch world_pkg:=heron_worlds world_pkg_file:=[WORLD_NAME].launch```
