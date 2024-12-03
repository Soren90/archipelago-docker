# Folders
* Players - Put player yamls here
* Roms - Put roms here
* Worlds - World folders/APWorld files

# Start
```
docker-compose up -d
```
# Generate game
```
docker-compose exec archipelago python Generate.py
```
# Copy zip file
```
docker-compose cp archipelago:/Archipelago/output/*.zip .
```
# Upload zip file to archpelago
https://archipelago.gg/uploads

# Advanced options
If you want to use another archipelago repo, you can use:
```
docker-compose build --build-arg repo=$REPOURL branch=$BRANCH
```
If you are adding new Roms or Worlds you need to rebuild the image again
```
docker-compose build
```
