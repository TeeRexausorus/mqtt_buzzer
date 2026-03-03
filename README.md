# Buzzer Control

## MQTT protocol

On a choisi d'utiliser des topics MQTT dédiés :
- buzzer/control
- buzzer/config

### buzzer/config
Ce topic est utilisé pour configurer ces valeurs globales :
 - "blocked_color", la couleur des buzzers bloqués, au format d'un tableau représentant les valeurs RVB (entre 0 et 255) [R, V, B] (Par exemple [255, 255, 0] pour du jaune)
 - "valid_color", la couleur du buzzer ayant la main, au format d'un tableau représentant les valeurs RVB (entre 0 et 255) [R, V, B] (Par exemple [0, 255, 0] pour du vert)

### buzzer/control
Ce topic est utilisé pour controler les buzzers en live :
 - "release" : sert à déverrouiller un/des buzzer•s, "" pour tous, sous forme de tableau pour 1 à plusieurs : [1, 2, ...]. En utilisant la numérotation "humaine", 1 à 5.
 - "lock" : Bloque "définitivement" (jusqu'à la sortie de "prison") le•s buzzer•s, sous forme de tableau aussi.
 - "unlock" : Débloque le•s buzzer•s listé•s dans le tableau passé.
