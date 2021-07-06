# Workshop-React-Native

<!-- Présentation du workshop
    Pré-requis
    Installation
    Projets/exo de base
    Css
    Dev Appli mobile
     -->

## Création d'une app Mobile.

Qu’est ce que react NATIVE ?

React NATIVE est un FrameWork open source qui permet de créer des applications mobile android/ios grâce à React. Il utilise des api javascript pour notre interface utilisateur à l’aide de composants react (« composant react est un block de code réutilisable ») prêt à l’emploi, créer ses propres components.
Rappel : Avant de commencer react NATIVE, il faut impérativement avoir des bonne notions en react, càd props , hooks , components , state…

### Pré-Requis

1. Nodejs.
2. Android studio / Expo.
3. ES7.
4. EXPO sur mobile.

### Installation

ce rendre sur le site : [expo](https://docs.expo.io/)

Expo sur desktop : 

1) Ce rendre sur votre cmd : ```npm install -g expo-cli –global```

2) Une fois l'installation expo fini ce rendre dans le directory de votre projet à l'aide du terminal : ```expo init nom-projet```

3) choisir un template : ici pour nos exercice et application on choisira "blank" enter 

4) lancer l'application : ```expo start``` 

Expo sur mobile :

Afin de pouvoir voir les resultats sur notre smartphone.

1) Ce rendre sur l'app store / play store installer expo.
2) Scaner le QRCODE apres avoir lancer expo start.

Alternative android studio (emulateur) :

ce rendre sur le site : [android](https://developer.android.com/studio)

Une fois l'installation réalisée :

1) Cliqué sur "Configure" sélectionné AVD manager
2) Crée un virtuel device
3) Category "phone" -> choisir un smartphone
4) Appuyer sur "next"
5) Choisir la version Android "Pie"

une fois l'installation de votre version fini lancer le virtuel devise, connectez-vous à votre compte google et installation expo voir étape au-dessus.

### Exercices :
 
Avant de commencer à développer notre premier application , commençon par quelque exercices.
Tout d'abord, après avoir crée votre projet aller sur le fichier "App.js".

```
import { StatusBar } from 'expo-status-bar';
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  return (
    <View style={styles.container}>
      <Text>Open up App.js to start working on your app!</Text>
      <StatusBar style="auto" />
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```
Ce code correspond au code pardéfaut de notre application il affiche simplement ce qu'il y a dans ``` <Text>Open up App.js to start working on your app!</Text> ```

Premier exemple :

Dans cet exercice nous allons voir comment utiliser les components de react Native ainsi que des hooks (useState).

Tout d'abord, nous allons avoir besoin de crée 2 useState.

```
import React,{useState} from 'react';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
   
   // definis les useState
  const [name,setName] = useState("Jhon");
  const [person ,setPerson] = useState({name: 'mario', age:40});

  return (
    <View style={styles.container}>
      // Afficher nos data ici 
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});
```

Ensuite pour afficher les données passé à nos useState.

```
import React,{useState} from 'react';
import { StyleSheet, Text, View } from 'react-native';

export default function App() {
  const [name,setName] = useState("Jhon");
  const [person ,setPerson] = useState({name: 'mario', age:40});

  return (
    <View style={styles.container}>
      <Text>My name is {name}</Text>
      <Text>His name is {person.name} his age {person.age}</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});

```

Jusqu'a present nous avons appris comment utiliser useState et afficher les donnée. Maintenant si nous voulons modifier une valeur que l'on passer à ceux-ci.

```
import React,{useState} from 'react';
import { StyleSheet, Text, View , Button } from 'react-native';

export default function App() {
  const [name,setName] = useState("Jhon");
  const [person ,setPerson] = useState({name: 'mario', age:40});

  const clickHandler = () => {
    setName("Ronny")
  }
  return (
    <View style={styles.container}>
      <Text>My name is {name}</Text>
      <Text>His name is {person.name} his age {person.age}</Text>
      <View>
        <Button title="update name" onPress={clickHandler}></Button>
      </View>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',
  },
});

```
