# **Projet Netflix-insights**

## Sommaire

- [**Projet Netflix-insights**](#projet-netflix-insights)
  - [Sommaire](#sommaire)
  - [**1** Veille sur l'intelligence artificielle](#1-veille-sur-lintelligence-artificielle)
    - [**1.1** Définitions](#11-définitions)
      - [**A** Intelligence artificielle](#a-intelligence-artificielle)
      - [**B** Apprentissage automatique :](#b-apprentissage-automatique-)
      - [**C** Pré-traitement des données :](#c-pré-traitement-des-données-)
      - [**D** Analyse descriptive des données :](#d-analyse-descriptive-des-données-)
    - [**1.2** L'intelligence artificelle dans différents domaines](#12-lintelligence-artificelle-dans-différents-domaines)
      - [**A** La santé :](#a-la-santé-)
      - [**B** La finance :](#b-la-finance-)
      - [**C** La recherche :](#c-la-recherche-)
  - [**2** Présentation du projet](#2-présentation-du-projet)
    - [**2.1** Contexte](#21-contexte)
    - [**2.2** Données utilisées](#22-données-utilisées)
  - [**3** Analyse des données Netflix de septembre 2021](#3-analyse-des-données-netflix-de-septembre-2021)
    - [**3.1** Observations](#31-observations)
    - [**3.2** Conclusions](#32-conclusions)


## **1** Veille sur l'intelligence artificielle

### **1.1** Définitions

#### **A** Intelligence artificielle

* ``Intelligence`` : 

Ensemble des processus trouvés dans des systèmes, plus ou moins complexes, vivant ou non, qui permettent d'apprendre, de comprendre ou de s'adapter à des situations nouvelles.

Le terme intelligence de la langue française est emprunté au latin intellĕgentĭa, lui-même dérivé du latin intellĕgō (« discerner, démêler, comprendre, remarquer ») dont le préfixe intĕr (« entre, parmi ») et le radical lĕgō (« ramasser, recueillir, choisir ») donnent le sens étymologique « choisir entre, ramasser parmi (un ensemble) » (ref : [Dictionnaire académie française](https://www.dictionnaire-academie.fr/article/A9I1608) / [wikipédia](https://fr.wikipedia.org/wiki/Intelligence))

* ``Artificiel`` : 

Qui est dû à la technique de l'homme, par opposition à ce qui a été crée et s'est développé naturellement. 

Le terme est emprunté du latin artificialis, "fait avec art, fait selon l'art". (ref: [Dictionnaire académie française](https://www.dictionnaire-academie.fr/article/A9A2706))

* ``Intelligence artificielle`` : 

L'**intelligence artificielle** est un ensemble de théories et de techniques visant à réaliser des machines capables de **simuler l'intelligence humaine**. (ref: [encyclopédie Larousse](https://www.larousse.fr/encyclopedie/divers/intelligence%20artificielle/187257))

Le terme, créé par **John McCarthy**, souvent abrégé par le sigle **IA** (**AI** en anglais), est définit par celui-ci ainsi : 

"_C'est la science et l'ingénierie de la fabrication de machines intelligentes, en particulier de programmes informatiques intelligents. Elle est liée à la tâche similaire qui consiste à utiliser des ordinateurs pour comprendre l'intelligence humaine, mais l'IA ne doit pas se limiter aux méthodes qui sont biologiqument observables._" (ref: [Article publié en 2004](https://www-formal.stanford.edu/jmc/whatisai.pdf))

Des décénies avant que cette définition ne soit donnée, la naissance de la conversatoin sur l'intélligence artificielle à été marquée par l'ouvrage fondateur d'**Alan Turing** publié en 1950, "[Computing Machinery and Intelligence](https://redirect.cs.umbc.edu/courses/471/papers/turing.pdf)". Dans cet article, M. Turing, souvent concidéré comme le père de l'informatique, propose la question suivante :

 "_Les machines peuvent-elles penser ?_".

Il propose ensuite un test, désormais connu sous le célèbre nom de "**Test de Turing**", dans lequel un interrogateur humain tente de différencier la réponse textuelle d'un ordinateur de celle d'un être humain. Bien que ce test ait fait l'objet d'un examen approfondi depuis sa publication, il reste un aspect important de l'histoire de l'IA ainsi qu'un concept permanent de la philosophie puisqu'il utilise des idées autour de la linguisitique. 

**Stuart Russel** et **Peter Norvig** ont ensuite publié [Intelligence artificielle : une approche moderne](https://aima.cs.berkeley.edu/), devenu l'un des principaux manuels d'étude de l'intelligence artificielle. Ils y explorent quatres objetcifs ou définitions potentiels de l'IA, qui différencient les systèmes informatiques sur la base de la rationalité et de la pensée par rapport à l'action : 
* **Approche humaine** : 
    * Des systèmes qui **pensent comme des humains** 
    * Des systèmes qui **agissent comme des humains**
* **Approche idéale** : 
    * Des systèmes qui **pensent de façon rationnelle**
    * Des systèmes qui **agissent de façon rationnelle**

La définition d'**Alan Turing** entrerait alors dans la catégorie des "**Systèmes qui agissent comme des humains**".

Dans sa forme la plus conscise, l'**IA est un domaine associant informatique à des ensembles de données fiables afin de faciliter la résolution de problèmes**.
Elle comprend égalment les sous-domaines du **marchine learning** et du **deep learning**, souvent utilisés en conjonction avec l'IA.
Ces diciplines sont constituées d'algorithmes d'IA cherchant à **créer des systèmes experts aboutissant à des prédictions ou des classifications** basées sur les **données entrantes**. (ref: [Qu'est ce que l'intélligence artificelle](https://www.ibm.com/fr-fr/topics/artificial-intelligence))

Pour l'**OCDE** (_Organisation de coopération et de développement économique_), un système d'IA est : 

" _un système basé sur une machine qui, pour des objectifs explicites ou implicites, déduit, à partir des informations qu'il reçoit, comment générer des résultats tels que des prédictions, du contenu, des recommandations ou des décisions, qui peuvent influencer les environnements physiques ou virtuels. Les différents systèmes d'IA varient dans leurs niveaux d'autonomie et d'adaptabilité après leur déploiement_" (ref: [Avis no 2024-01 du 17 janvier 2024 pour mieux encadrer l’usage de l’intelligence artificielle, CSNP, 21 p.](https://csnp.fr/wp-content/uploads/2024/01/AVIS-N%C2%B02024-01-du-17-JANVIER-2024-pour-mieux-encadrer-lusage-de-lintelligence-artificielle-2.pdf))

Il existe une confusion dans le débat publique entre **intelligence artificielle**, **aprentissage automatique** (_machine learning_) et **aprentissage profond** (_deep learning_). Pourtant ces notions ne sont pas équivalente, mais imbriquées. L'IA englobe l'aprentissage automatique, qui lui-même englobe l'aprentissage profond. (ref: [Intelligence artificielle, machine learning, deep learning : kézako ?](https://www.ledigitalab.com/2017/10/02/intelligence-artificielle-machine-learning-deep-learning-kezako/))

#### **B** Apprentissage automatique :

L'**apprentissage automatique** (_machine learning_), **apprentissage artificiel** ou **apprentissage statistique** est un champ d'étude de l'**intelligence artificiell** qui se fonde sur **des approches mathématiques et statistiques** pour donner aux ordinateurs la **capacité d'apprendre à partir de données**, c'est à dire d'**améliorer leurs performances à résoudre des tâches sans être explicitement programmées pour chacune.**

Plus largement, il concerne **la conception**, **l'analsyse**, **l'optimisation**, **le développement** et **l'implémentation** de telles méthodes.

On parle **d'aprprentissage statistique** car l'apprentissage consiste à **créer un modèle dont l'erreur _statistique moyenne_ est la plus faible possible**. 

L'**apprentissage automatique** comporte généralement deux phases : 

* **Estimer un modèle** à partir de données, appelées **observations**, qui sont disponibles et en nombre fini, lors de la phase de conception du système.
L'estimation du modèle consiste à **résoudre une tpache pratique**, telle que traduire un discrous, estimer une densité de probabilité, reconnaître la présence d'un chat dans une photographie ou participer à la ocnduite d'un véhicule autonome.
Cette **phase d'apprentissage ou d'entraînement** est généralement réalisée préalablement à l'utilisation pratique du modèle.

* **Mise en production**, le modèle étant déterminé, de **nouvelles données** peuvent alors être soumises afin d'**obtenir le résultat correspondant à la tâche souhaitée**.En pratique, certains systèmes peuvent pooursuivre leur apprentissage une fois en production, pour peu qu'ils aient un moyen d'obtenir un **retour sur la qualité des résultat produits**. (ref: [wikipédia](https://fr.wikipedia.org/wiki/Apprentissage_automatique))

En fonction des informarmations disponibles durant la phase d'apprentissage, l'apprentissage peut être qualifié de différentes façons : 

* [Apprentissage supervisé](https://fr.wikipedia.org/wiki/Apprentissage_supervis%C3%A9) : si **les données sont étiquetées** (la **réponse à la tâche est connue** pour ces données).

* [Classification ou classement](https://medium.com/le-blog-de-lapprentissage-automatique/quest-ce-que-la-classification-43744b75f546) : si **les étiquettes sont discrètes**.

* [Régression](https://fr.wikipedia.org/wiki/R%C3%A9gression_(statistiques)) : si **les étiquettes sont continues**.

    * Différence entre des variables discrètes et continues :

    Aspect | Varibales Discrète | Varibales Continues
    ---: | :---: | :---
    Sens | Espaces vides entre les valeurs | Séquence continues
    Nature | Dénombrable | Mesurable
    Valeurs | Valeurs distinctes ou séparées | Toute valeurs dans un intervalle
    Représentation graphique | Graphique à barres | Histogramme

* [Aprentissage par renforcement](https://fr.wikipedia.org/wiki/Apprentissage_par_renforcement) : Si le **modèle est appris de manière incrémentale en fonction d'une récompense reçue par le rpogramme pour chacune des actions entreprises**.

* [Apprentissage non supervisé](https://fr.wikipedia.org/wiki/Apprentissage_non_supervis%C3%A9) : Dans le cas le plus général, **sans étiquettes**, on cherche à **déterminer la structure sous-jacente des données** (pouvant être une densité de probabilité).

L'*apprentissage automatique** peut être appliqué à **différents types de données**, tels que des **graphes**, des **arbres**, des **courbes**, ou plus simplement des **vecteurs de caractéristiques**, pouvant être des variables **qualitatives** ou **quantitatives**, **continues** ou **discrètes**. 


#### **C** Pré-traitement des données :

Le **prétraitement des données** peut faire référence à la **manipulation** ou à la **suppression** de données **avant leur utilisation** afin d'**assurer** ou d'**améliorer** les performances, il s'agit d'une étape important du **processus d'exploration de données** et d'une des phases les plus importantes d'un projet d'**apprentissage automatique**.

L'idée dominante étant d'éviter, lors des méthodes de **collecte des données** souvent mal contrôlées, les valeurs hors limites, les combinaisons impossibles ou les valeurs manquantes. 

Le déroulement du **prétraitement des données** peut être décrit par les tâches suivantes :

* [Nettoyage](https://fr.abcdef.wiki/wiki/Data_cleansing) des données.
* [Edition](https://fr.abcdef.wiki/wiki/Data_editing) de données.
* [Réduction](https://fr.abcdef.wiki/wiki/Data_reduction) de données.
* [Dispute](https://fr.abcdef.wiki/wiki/Data_wrangling) de données. 

(ref : [https://fr.abcdef.wiki/wiki/Data_pre-processing])


#### **D** Analyse descriptive des données :

L'**analyse descriptive** est le **processus de transformation des données en informations**. 

Cela permet de prendre du recul et de comprendre ce qu'il s'est passé afin de prendre de meilleurs décisions.

Il s'agit d'un type d'analyse de données utilisé pour **décrire** et **comprendre** les données, permettant ainsi de comprendre les **modèles** et les **tendances** des données afin de prendre de meilleurs décisions. 

L'**analyse descriptive** est pafois confondue avec l'**analyse prédictive**, la première est utilisée pour répondre à la question "_qu'est ce qu'il s'est passé ?_, tandis ce que la seconde pour prédire ce qu'il se passera dans le futur. 

Il existe plusieurs types d'analyses descriptives, les plus courants étants :

* **L'analyse statistique** : Utilisée pour **comprendre ce q'il se passe dans un ensemble de données** et **trouver des relations entre différentes variables**.

* **La visualisation** : Utilisée pour **créer des graphiques et des diagrammes** permettant de **meixu comprendre les données**. Elle identifie les **tendances** et les **modèles** et met en lumière comment **les différentes variables agissent entre elles.**

* **Statistique descriptive** : Utilisées pour **résumer les données**, elles permettent de trouver la *moyenne**, la **médiane** et le **mode** d'un ensemble de données, ainsi que la **variance** et **l'écart type**.

* **Moyennes** : Utilisée dans le but de **fournir la valeur moyenne d'un ensemble de données**, elle permet de trouver la **moyenne**, la **médiane**, le **mode** et la **moyenne pondérée** d'un ensemble de données. 

(ref : [Analyse descriptive](https://timetodata.com/definitions/analyse-descriptive/))

### **1.2** L'intelligence artificelle dans différents domaines 

#### **A** La santé :

L'**intelligence artificielle dans la santé** est l'utilisation d'algorithmes et de logiciels pour s'approcher de la cognition humaine dans l'analyse de données médicales complexes. Plus précisément, l'IA dans ce domaine consiste en la **capacité des algorithmes informatiques à tirer des conclusions sans intervention humaine directe**.

=> L'objectif principal des applicaiton des IA dans le domaine dela santé est d'**analyser les relations entre, d'une part, la prévention ou les traitements et, d'autre part, l'état de santé des patients**.

Les programmes d'intelligence artificielle on été développés et appliqués à des pratiques telles que : 

* Le processus de **diagnostique**.
* L'élaboration d'un **protocole de traitement**.
* Le **développement de médicaments**.
* La **médecine personnalisée**.
* Les **soins** et le **suivi** des patients.

On peut les retrouver dans les domaines suivants : 

* **Radiologie**.
* **Psychiatrie**.
* **Cancérologie**.
* **Télésanté**.
* **Maladies chroniques et éducation thérapeutique**.
* **Indusrtrie**.


Bien que la recherche sur l'utilisation de l'IA dans les soins de santé tend à démontrer son efficacité dans l'*amélioration des résultats** pour le patient, son utilisation peut néanmoins introduire **plusieurs nouveaux types de problématiques** pour les patients et les fournisseurs de soins de santé, comme les [**biais algorithmiques**](https://fr.wikipedia.org/wiki/Biais_algorithmique) (Fait que le résultat d'un algorithme ne soit pas neutre, loyal ou équitable que ce soit de manière inconsciente ou délibérée), les question liées aux ordoannances de "ne pas réanimer", et d'autres questions de moralité des machines.
Ces défis posent la question d'un potentiel **besoin de réglementation**.

Depuis le début des années 2020, les **usages de l'IA et de l'apprentissge automatique** sont en pleinne expansion dans la pluspart des champs de la santé.
Cependant il faut s'attendre à des **dilemmes et défis éthiques complexes ou imprévus** sur les questions de **partialité**, de **protection des données et de la vie privée**, de l'**anonymat**, du **consentement éclairé**, de la **confidentialité et de la sécurité**, du **manque de transparence et d'explicabilité** ainsi que des **impacts potentiels sur les relations médecin-patient**...

Des **biais ([raciaux](https://www.emerald.com/insight/content/doi/10.1108/JICES-06-2018-0056/full/html) et [autres](https://aiej.org/aiej/article/view/1)) à l'empathie en passant par la compassion, l'IA suscite de **nombrux débats philosophiques, éthiques et moraux**.

Les **problèmes éthiques** de l'IA en général se croisent avec les **quatre piliers de l'héthique médicale** :

* L'**autonomie**.
* La **justice**.
* La **bienfaisance**.
* La **non-malfaisance**.

(ref : [Wikipedia](https://fr.wikipedia.org/wiki/Intelligence_artificielle_dans_la_sant%C3%A9))

#### **B** La finance :

L'**intelligence artificielle appliquée à la finance** consiste en l'utilisation de technologies, notamment d'algorithmes avancés et de machine learning, pour **analyser les données, automatiser les tâches et améliorer la prise de décision dans le secteur des services financiers**.

Il existe plusieurs **domaines d'application de l'IA dans le secteur financier** tel que : 

* **Trading algorithmique**.
* **Automatisation et efficacité**.
* **Avantage concurrentiel**.
* **Conformité**.
* **Evaluation du crédit**.
* **Réduction des coûts**.
* **Service client**.
* **Analyse des données**.
* **Détection des fraudes**.
* **Traitement des prêts**.
* **Finances personnelles**.
* **Gestion de portefeuilles**.
* **Analyse prédictive**.
* **Gestion des risques**.
* **Analyse des sentiments**.

Les **principaux acteurs de l'IA dans la finance** sont : 

* **Des auditeurs et équipes de contrôle internes.**
* **Des directeurs des systèmes d'information (DSI) et des directeurs techniques**.
* **Des clients**.
* **Des développeurs**.
* **Des responsables de l'éhtique et de la diversité**.
* **Des cadres**.
* **Des organismes financiers**.
* **Des équipes juridiques**.
* **Des équipes de gesition du risque**.

Dans le **cadre de la finance**, l'IA nécessite une **surveillance pour garentir une utilisation appropriée et un risque minimal**.
Une **gouvernance proactive** peut favoriser une **utilisation responsable**, **éthique** et **transparente** de l'IA, ce qui est essentiel lorsque les institutions financières traitents de **grandes quantités de données sensibles**.

(ref : [IBM](https://www.ibm.com/fr-fr/topics/artificial-intelligence-finance))

#### **C** La recherche :

L'**IA à considérablement transformée la recherche scientifique**.

Avec ses **capacités avancées en matière de traitement des données, d'apprentissage automatique et d'analyse prédictives**, l'IA offre des opportunités sans précédent pour **accélérer les découvertes scientifiques**.

Des domaines tels que la **biologie**, la **physique**, la **chimie** et bien d'autres bénéficient des avantages de l'IA. Cela permet aux chercheurs d'**explorer des questions coplexes** et de **résoudre des problèmes auparavant insolubles**.

Cette avancée technologique prometteuse ouvre de **nouvelles perspectives** passionnantes pour l'avenir de la recherche scientifique et offre des possiblitiés de progès révolutionnaires.

(ref : [lebigdata](https://www.lebigdata.fr/ia-recherche-scientifique))


## **2** Présentation du projet
### **2.1** Contexte
### **2.2** Données utilisées

## **3** Analyse des données Netflix de septembre 2021

### **3.1** Observations

### **3.2** Conclusions
