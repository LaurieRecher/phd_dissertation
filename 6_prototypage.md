# Chapitre 6 : prototypage d'une intervention en systèmes d'information à partir des kernel theories et permettant de faciliter les interactions homme-données

Dans le chapitre précédent, nous avons détaillé le processus de design qui, à partir des besoins fonctionnels des opérateurs de l'open data, nous a permis d'identifier des *kernel theories* pour guider le design d'intervention en systèmes d'information permettant de répondre à la question de recherche. Nous avons également pu identifier dans la littérature un certain nombre d'éléments fonctionnels que l'intervention devra nécessairement intégrer pour assurer le passage de la situation problématique à la situation désirée (Carlsson, 2010, p.220). Ensemble, ces deux éléments nous ont permis de déterminer un modèle de design et de le rattacher à une classe (Offerman et al., 2010). 

L'objet de ce chapitre est d'assurer le passage de la dimension conceptuelle à la dimension matérielle. Autrement dit, il s'agit de mettre en oeuvre un processus d'instanciation qui permet "d'implémenter des fonctionnalités dans un objet à partir d'une structure prédéfinie et pré-optimisée" (Cofer et Harding, 2006, p.120). 

Pour chacune des itérations de cette thèse, nous suivrons un processus d'instanciation basé sur une actualisation des travaux de Ince et Hekmatpour (1987). Ces derniers ont défini un process en trois étapes :  

  1. Définir les objectifs du prototype relativement au projet de recherche 
  2. Sélectionner les fonctions du prototype à mettre en oeuvre 
  3. Construire le prototype 

Or, ce processus a été développé pour le prototypage de logiciels informatiques, des artefact produits, tandis que cette thèse vise à prototyper une intervention qui combine des produits et des process. Pour cette raison, nous avons ajouté une quatrième étape au processus qui permet de satisfaire cette particularité des interventions en système d'information.  De plus, les seuls moyens de mise en place du processus mentionnés par Ince et Hekmatpour (1997) sont des langages et des méthodes formelles propres aux sciences informatiques et à la programmation. Or, les compétences et ressources à disposition de ce travail de thèse ne nous permettent pas d'utiliser de telles méthodes. Par conséquent, nous avons du contourner ce manque de compétences et de ressources. En lieu et place des langages de programmation, nous avons utilisé des outils logiciels (Ince et Hekmatpour, 1987, p.11). Ces outils sont des programmes qui ne nécessitent pas d'avoir des compétences de programmation mais à partir desquels il est possible de construire un logiciel. En lieu et place des méthodes formelles faisant appel aux mathématiques, nous avons utilisé des *pattern* de prototypage développés par Vaishnavi et Kuelcher (2015, p.119-156). 

Finalement, pour chaque itération, nous suivrons un processus en quatre étapes et utiliserons comme moyen de mise en place des étapes des *pattern* de prototypage et des outils logiciels : 

  1. Définir les objectifs du prototype relativement au projet de recherche 
  2. Sélectionner les fonctions du prototype à mettre en oeuvre 
  3. Construire le prototype 
  4. Etablir les mécanismes permettant de venir implémenter le prototype dans un contexte d'usage réel

 ### 1ère étape : définir les objectifs du prototype vis à vis de la recherche et le type de prototypage

Dans la première étape, il s'agit de déterminer ce que nous cherchons à accomplir avec le prototype vis à vis du projet de recherche. 
Trois alternatives s'offrent à nous (Carey et Mason, 1983). Un prototype peut avoir pour objectif de préciser la compréhension des besoins fonctionnels des futurs utilisateurs du prototype (*improved functional requirements*). Dans ce cas, le prototype devient un intermédiaire, un moyen d'apprentissage, une loupe d'observation au service de la compréhension des besoins des utilisateurs. Aussi, un prototype peut avoir pour objectif d'améliorer les interactions entre ce dernier et les utilisateurs (*improved interaction requirements*). Il est fréquent qu'un prototype ne soit pas utilisé du fait du design de l'interface qui décourage les utilisateurs. Dans ce cas, on intègre de nouvelles interfaces de façon à améliorer les interactions entre l'utilisateur et l'artefact. Enfin, un chercheur peut mettre en place un prototype pour s'assurer de sa capacité à s'adapter aux évolutions des besoins des utilisateurs (*easier evolution of requirements*). On conçoit alors un système indéfini, qui peut prendre plusieurs formes en fonction des contextes d'usage et de leur évolution. Les systèmes d'aide à la décision sont de bons exemples de systèmes indéfinis qui peuvent être façonnés au gré des situations rencontrées par les utilisateurs. 

#### Choix d'un type de prototypage (throw-it-away, incremental, evolutionnary)
 
Le choix de ces objectifs va avoir une incidence sur le type de prototypage mis en place. De ce fait, dans la première étape, nous définirons également, pour chaque itération, le type de prototypage qui sera mis en place.

On distingue le prototypage *throw-it-away*, le prototypage incrémental et le prototypage évolutif. Le prototypage throw-it-away est mis en place pendant la période de compréhension des besoins fonctionnels des utilisateurs. Il permet d'obtenir un objet très rapidement que les utilisateurs peuvent évaluer. Dans la plupart des cas, l'objet est rapidement écarté (*thrown away*) car de nouveaux besoins fonctionnels ont été identifiés (ce qui donne son nom à ce type de prototypage). Comme indiqué dans le tableau X, ce type de prototypage est adapté quand les objectifs sont de mieux comprendre les besoins des utilisateurs et d'améliorer les interactions avec l'artefact. Le prototypage incrémental est quant à lui utilisé quand les concepteurs ont décidé d'un modèle d'artefact et figé le liste des besoins fonctionnels des utilisateurs. Il s'agit alors de subdiviser le modèle et de construire chaque partie progressivement. Ce type de prototypage permet de se rendre compte rapidement des erreurs et des problèmes d'implémentation qui peuvent apparaitre pour les résoudre avant de créer l'artefact final. Comme indiqué dans le tableau X, ce type de prototypage est uniquement utilisé quand le but est d'améliorer les relations entre les utilisateurs et l'artefact. En effet, en mettant en place successivement chaque partie, il est possible de régler au cas par cas les frictions qui peuvent naitre entre l'artefact et les utilisateurs. Enfin, le prototypage évolutif est le type le plus flexible. Il consiste à développer un système graduellement qui puisse s'adapter à des changements substantiels et souvent inévitables : modification des besoins fonctionnels, changement du cadre juridique, des organisations ou encore précision des *kernel theories* utilisées pour guider le design. Comme indiqué dans le tableau X, ce type de prototypage est adapté quelque soit les objectifs. 


<table>
    <thead>
        <tr>
            <th></th>
            <th>Prototypage throw-it-away</th>
            <th>Prototypage incrémental</th>
            <th>Prototypage évolutif</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <th>Improved functional requirements</th><th>X</th><th></th><th>X</th>
      </tr>
      <tr>
        <th>Improved interaction requirements</th><th>X</th><th>X</th><th>X</th>
      </tr>
      <tr>
        <th>Easier evolution of requirements</th><th></th><th></th><th>X</th>
      </tr>
  </tbody>
</table>

##### Figure. Tableau de correspondance entre les objectifs et les types de prototypage.   
  
### 2ème étape : sélectionner les fonctions du prototype (classées par élément fonctionnel)

La deuxième étape consiste à sélectionner, par élément fonctionnel, les fonctions qui seront protoypées. Pour effectuer ce choix, nous utiliserons les critères du pattern *Easy solution first* (Vaishnavi et Kuelcher, 2015, p.131). Ce pattern vise à toujours privilégier les fonctions faciles à mettre en oeuvre en période de prototyage. Ainsi, nous sélectionnerons les fonctions pour lequels il existe une solution de prototypage facile à mettre en oeuvre et à évaluer. Autrement dit, nous priviligierons les fonctions qui peuvent être facilement mise en place par des outils logiciels connus et ne nécessitant pas de connaissances techniques. Cette façon de sélectionner les fonctions a notamment été choisi par Berners-Lee and Cailliau (1990) quand ils ont présenté pour la première fois le concept de *World Wide Web*. Internel était dépeint comme une combinaison de 2 éléments fonctionnels (un navigateur et un serveur) avec des fonctions simples : le navigateur a pour fonction de lire des liens hypertextextes qui correspondent à des noeuds d'un réseau et de garder un historique des liens lus ; le serveur, quant à lui, stocke tous les réseaux de noeuds et négocie avec le navigateur le format sous lequel les liens peuvent être lus. 

### 3ème étape : construire le prototype

La 3ème étape consiste à construire concrètement le prototype, c'est à dire à mettre en place les fonctions sélectionnées selon le type de prototypage choisi. Comme mentionné précedemment, nous utiliserons des outils logiciels pour prototyper chaque fonction. Plus précisément, nous utiliserons des outils configurables à partir d'un tableur excel ou Google sheet du fait que ces outils sont connus et utilisé de tout le monde. Cette diffusion massive facilitera la prise en main des prototype par l'ensemble des concepteurs impliqué dans cette thèse mais aussi la future implémentation dans des situations réelles. Il sera en effet d'autant plus facile de mettre en place ces artefacts si les utilisateurs peuvent être rapidement en capacité de configurer ses fonctions au gré de leurs envies. 

#### Architecture (modèle simple) - rappel phase design
  
Dans cette construction, nous reprendrons le modèle de design créé et les éléments fonctionnels identifiés dans le chapitre 5 pour dessiner à partir de là une architecture générale du prototype. Nous diviserons ensuite cette architecture en différents aires fonctionnelles dans lesquelles nous viendrons placer les fonctions sélectionnées. Alors, nous suivrons le pattern des *Building Blocks* (Vaishnavi et Kuelcher, 2015, p.138). Il préconise de décomposer chaque fonction en fonctions plus petite jusqu'à ce que correspondent à chaque fonction un outil logiciel dédié pouvant construire la fonction. Ensuite, il s'agit de construire la fonction puis de les assembler récursivement jusqu'à que toutes les fonctions soient assurées et que les aires fonctionnelles soient opérationnelles.

#### Operations/Prototypage des interfaces
  
Une fois le prototype construit, il s'agit de rédiger des scénarios d'utilisabilité, indépendant du contexte d'usage, qui permettent de dessiner le fonctionnement opérationnel du prototype et montre sa facilité d'utilisation (Pascal et Rouby, 2006). Il permet de simuler la façon dont les diverses fonctions opérent en interactions avec l'utilisateur. On trouve également dans ces scénarios des prototypes d'interfaces utilisateurs qui permettent de se rendre compte de l'aspect visuel des fonctions et du point de vue de l'utilisateur lorsqu'il les utilise. 

 ### 4ème étape. Etablir les mécanismes permettant de venir implémenter le prototype dans un contexte d'usage réel

Etant donné que nous prototypons des interventions, il est aussi question de s'interroger sur les approches de mise en place du prototype et son utilité dans un contexte particulier : celui de la réutilisation de l'open data dans les villes intelligentes. Il s'agit alors, au delà de s'interroger sur l'utilisabilité de l'outil, de question son utilité et d'établir les mécanismes qui permettent de lier les deux. Ces mécanismes seront dessinées dans des scénarios d'usage pour chacune des itérations de cette thèse. 
