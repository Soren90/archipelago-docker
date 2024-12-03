# Instructions
This is an easy to use Dockerfile for setting up archpelago with custom ApWorlds (beta games) on your local machine. You can then generate a custom game that you can upload to archipelago.gg.

Some games require ROM files to be able to be generated.

# Folder structure
* Players - Put player yamls here
* Roms - Put roms here
* Worlds - World folders/APWorld files

# Start local server
```
docker compose up -d
```
Access the site on http://localhost

# Generate game
Make sure all of your player yamls and roms are added to their respective folders.
```
docker compose exec archipelago python Generate.py
```
Your custom game will be located in the output folder

# Upload zip file to archpelago
To play the game on the main archipelago site, you need to create your game with the following URL:

https://archipelago.gg/uploads

# Advanced options
If you want to use another archipelago repo, you can use:
```
docker compose build --build-arg repo=$REPOURL branch=$BRANCH
```
If you are adding new Roms or Worlds you need to rebuild the image again
```
docker compose build
```

If you want to be able to generate games on your local instance, you need to use network_mode: host in the docker-compose.yaml file, as every game will use a random port for the game.
