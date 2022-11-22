# m1Info-verif

## Récupération de l'image

docker pull fdabrowski/why3:0.1

## Exécution de l'image (nécessite un répertoire local why3 dans votre home)

xhost +"local:docker@"

docker run -it --privileged --env DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix -v /home/dabrowski/why3:/home/user/why3 why3:0.1

xhost -"local:docker@"

(**) si vous n'etes pas membre du groupe, utilisez 'xhost +' et 'xhost -'

## utilisatio de why3 

depuis le répertoire why3
  
(**) le fichier contenant le programme à vérifier doit exister avant (touch filename.mlw)
  
  why3 ide filename.mlw
  
  
