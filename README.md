# MobileNet-SSD-Sujet13
Partage du groupe 7 projet IA <br>
Ce projet est inspiré de [Pensée Artificielle](https://penseeartificielle.fr/mobilenet-ssd-identifier-objets-camera-smartphone/)

## Contact 

* Jules Bangard, [JulesBa-Git](https://github.com/JulesBa-Git) 
* Adnan Mustafic, [Sticamuf](https://github.com/Sticamuf) 
* Julien Froelich-Thaler, [Soccrate](https://github.com/Soccrate)
* Lucas Aissaoui, [AissAiss](https://github.com/AissAiss)

## Table des matières 

<ul>
	<li><a href="#Install">Installation</a>
        <ul>
            <li><a href="#creatoin">Création de l'environement</a></li>
            <li><a href="#paquets">Installation des paquets</a></li>
            <li><a href="#tf">Tensorflow</a></li>
            <li><a href="#protoc">Protocol Buffer</a></li>
        </ul>
    </li>
    <li><a href="#Test">Tests</a></li>
        <ul>
            <li><a href="#jupyter">Test avec Jupyter Notebook</a></li>
            <li><a href="#video">Test avec une vidéo</a></li>
        </ul>
    <li><a href='#Entrainer'>Entrainer un modèle</a></li>
    
</ul>


# Installation
<a id='Installation'></a>

Dans cette partie, nous allons voir les paquets à installer pour utiliser le projet sur votre machine. 

Tout d'abord, dans ce projet nous utiliserons Anaconda, si il n'est pas installé sur votre machine, je vous invite à suivre cette vidéo pour installer [Anaconda](https://www.youtube.com/watch?v=jaw5FhWx2Bk&ab_channel=MachineLearnia) et à revenir ici pour suivre les prochaines étapes.

## Création de l'environnement 
<a href='creatoin'></a>

Une fois installé, ouvrez Anaconda Prompt puis créer un nouvel environement pour le projet. 

```shell 
(base) C:\Users\AissAiss>conda create -n projetMB python=3.6 pip 
```
Une fois votre environement créé il vous faut l'activer. 

```shell 
(base) C:\Users\AissAiss>conda activate projetMB
(projetMB) C:\Users\AissAiss>
```
Votre environement est bien activé si son nom apparait entre paranthèse à gauche.

## Instalation des paquets nécessaires
<a href='paquets'></a>

Une fois dans votre environement, il vous faudra installer les paquets suivants.

```shell 
(projetMB) C:\Users\AissAiss>pip install pillow==8.0.1
```
Pillow est une library de manipulation d'images, qui permet de travailler efficacement dessus.

```shell 
(projetMB) C:\Users\AissAiss>pip install lxml==4.6.1
```
Permet de travailler sur du xml et du html

```shell 
(projetMB) C:\Users\AissAiss>pip install jupyter==1.0.0
```
Jupyter étant déjà installé par défaut avec Anaconda, nous allons juste nous assurer qu'il soit bien sur votre machine. 

```shell 
(projetMB) C:\Users\AissAiss>pip install matplotlib==3.3.3
```
Mathplotlib permet de tracer des graphes et est utilisé par beaucoup d'autres librairies.

```shell 
(projetMB) C:\Users\AissAiss>pip install opencv-ptyhon==4.4.0.46
```
Opencv-python est une librairie d'analyse d'image. 

## Installation de Tensorflow et tensorflow-gpu
<a href='tf'></a>

L'installation de Tensorflow étant un peu plus complexe et ne se résume pas simplement à un pip install. En effet, nous avons besoin d'installer les deux librairies suivantes :  

<ul>
    <li><a>CUDA Toolkit 9.0</a></li>
    <li><a>CDNN 7.0.5</a></li>
</ul>

Pour se faire, nous vous conseillons de suivre cette [vidéo](https://www.youtube.com/watch?v=uIm3DMprk7M&t=113s&ab_channel=MarkJay) **restant toujours dans votre environement**. 

Une fois ceci fait, vous êtes prêts à installer tensorflow : 
```shell 
(projetMB) C:\Users\AissAiss>pip install tensorflow==1.5
(projetMB) C:\Users\AissAiss>pip install tensorflow-gpu==1.5
```

Votre environnement est désormais prêt pour la suite ! 

## Protocol buffer
<a href='protoc'></a>

Pour ce projet, nous avons besoin de travailler avec des protocol buffers, c'est un format de sérialisation avec un langage de description d'interface développé par Google. Il va nous permettre de créer un modèle et de le partager avec n'importe quel langage assez facilement. 
Je vous conseille de télécharger la version [3.4.0](https://github.com/google/protobuf/releases/download/v3.4.0/protoc-3.4.0-win32.zip)

Une fois le téléchargement effectué, il vous suffira de dézipper le dossier et de le placer dans le dossier de votre choix ; attention il faudra par la suite ajouter le dossier au path de Windows. Voici une [vidéo](https://www.youtube.com/watch?v=XkErKaltd6E&ab_channel=ThinkSalesforce) expliquant la procédure. 

Pour la suite, nous devons nous placer dans le dossier research. 

```shell 
(projetMB) C:\Users\AissAiss> cd VOTREPATH/research/
```

Nous utiliserons l'arborescence D:\workspace\models\research

```shell 
(projetMB) C:\Users\AissAiss> cd  D:\workspace\models\research
(projetMB) D:\workspace\models\research>
```

Nous sommes prêts pour initialiser le projet avec les commandes suivantes.
La commande suivante permet de construire les fichiers proto. 

```shell 
(projetMB) D:\workspace\models\research>protoc object_detection/protos/*.proto --python_out=.
```

Désormais, il faut définir l'environnement de travail python, il faut également l'adapter à votre arborescence. 

```shell 
(projetMB) D:\workspace\models\research>set PYTHONPATH=VOTREPATH\research;VOTREPATH\research\slim
```

Puis pour finir, nous devons lancer l'installation du projet. 

```shell 
(projetMB) D:\workspace\models\research>python setup.py install
```

Si toutes les commandes se sont bien passées, nous pouvons passer aux tests ! 

# Tests
<a id='Test'></a>

Dans ce projet, il a deux moyens de tester votre environnement, la première avec Jupyter Notebook permet de visualiser le code. 

## Test avec Jupyter Notebook 
<a href='jupyter'></a>

Placez vous dans le dossier objet_detection, puis lancez Jupyter Notebook 

```shell 
(projetMB) D:\workspace\models\research>cd objet_detection
(projetMB) D:\workspace\models\research\objet_detection>jupyter notebook
```
Une page web devrait s'ouvrir dans votre navigateur par défaut, cliquez sur “object_detection_tutorial.ipynb” puis dans le menu Cell cliquez sur Run All. 

Si tout se passe bien, vous devriez voir toutes les cellules avec un numéro entre crochet à gauche et les premières images labellisées par notre modèle devrait apparaitre en bas de la page. Si cette étape vous pose problème je vous conseille de copier/coller votre message d'erreur sur google, cela reste le meilleur moyen de résoudre un problème à cette étape. [Stackoverflow](https://stackoverflow.com/) est souvent de bon conseil ;)

## Test avec une vidéo  
<a href='video'></a>

Toujours avec votre environnement activé, et dans le dossier objet_detection vous pouvez lancer le programme suivant. 

```shell 
(projetMB) D:\workspace\models\research\objet_detection>python test-video-example.py
```

# Entrainer un modèle 
<a href="Entrainer"></a>

Pour entrainer un modèle,




