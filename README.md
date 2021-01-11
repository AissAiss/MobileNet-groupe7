# MobileNet-SSD-Sujet13
Partage du groupe 7 projet IA 
Ce projet est inspiré de 

## Contact 

* Jules Bangard, []() 
* Adnan Mustafic, [Sticamuf](https://github.com/Sticamuf) 
* Julien Froelich-Thaler, []()
* Lucas Aissaoui, [AissAiss](https://github.com/AissAiss)

## Table des matières 

<ul>
	<li><a href="#Install">Installation</a>
        <ul>
            <li><a href="creatoin">Céation de l'environement</a></li>
            <li><a href="paquets">Instalation des paquets</a></li>
            <li><a href="tf">Tensorflow</a></li>
            <li><a href="protoc">Protocol Buffer</a></li>
            <li><a href="obj">Objet-detection de tensorflow</a></li>
        </ul>
    </li>
    <li><a href="#Test">Tests</a></li>
    <li><a href='#Entrainer'>Entrainer un modèle</a></li>
    
</ul>


# Installation
<a id='Installation'></a>

Dans cette partie nous allons voir les paquets à installer pour utiliser le projet sur votre machine. 

Tout d'abord dans ce projet nous utiliserons Anaconda, si il n'est pas installer sur votre machine je vous invite à suivre cette vidéo pour installer [Anaconda](https://www.youtube.com/watch?v=jaw5FhWx2Bk&ab_channel=MachineLearnia) et à revenir ici pour suivre les prochaines étapes.

## Création de l'environement 
<a href='creatoin'></a>

Une fois installé, ouvrez Anaconda Prompt puis créer un nouvelle environement pour le projet. 

```shell 
(base) C:\Users\AissAiss>conda create -n projetMB python=3.6 pip 
```
Une fois votre environement créer il vous faut l'activer. 

```shell 
(base) C:\Users\AissAiss>conda activate projetMB
(projetMB) C:\Users\AissAiss>
```
Votre environement est bien activé si son nom apparait entre paranthèse à gauche.

## Instalation des paquets nécessaires
<a href='paquets'></a>

Une fois dans votre environement il vous faudra installer les paquets suivants.

```shell 
(projetMB) C:\Users\AissAiss>pip install pillow
```
Pillow est une library de manipulation d'images, qui permet de travailler efficacement dessus.

```shell 
(projetMB) C:\Users\AissAiss>pip install lxml  
```
Permet de travailler sur du xml et du html

```shell 
(projetMB) C:\Users\AissAiss>pip install jupyter
```
Jupyter étant déjà installé par default avec Anaconda, nous allons juste nous assurer qu'il soit bien sur votre machine. 

```shell 
(projetMB) C:\Users\AissAiss>pip install matplotlib
```
Mathplotlib permet de tracer des graphes et est utilisé par beaucoup d'autres librairies.

```shell 
(projetMB) C:\Users\AissAiss>pip install opencv-ptyhon
```
Opencv-python est une librairie d'analyse d'image. 

## Installation de Tensorflow 
<a href='tf'></a>

L'installation de Tensorflow étant un peu plus complex, je vous conseille donc de suivre cette [vidéo](https://www.youtube.com/watch?v=uIm3DMprk7M&ab_channel=MarkJay) en **restant toujours dans votre environement**. 


## Protocol buffer
<a href='protoc'></a>

Pour ce projet nous avons besoin de travailler avec des protocol buffers, c'est un format de sérialisation avec un langage de description d'interface développé par Google. Il va nous permettre de créer un modèle et de le partager avec n'importe quel language assez facilement. 
Je vous conseille de télécharger la version [3.4.0](https://github.com/google/protobuf/releases/download/v3.4.0/protoc-3.4.0-win32.zip)

Une fois le téléchargement effectué il vous suffira de dézipper le dossier et de le placer dans le dossier de votre choix attention il faudra par la suite ajouter le dossier au path de Windows. Voici une [vidéo](https://www.youtube.com/watch?v=XkErKaltd6E&ab_channel=ThinkSalesforce) explicant la procedure. 

## Objet-detection de tensorflow
<a href='obj'></a>




# Tests
<a id='Test'></a>




