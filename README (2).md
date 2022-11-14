# (Données de prets de Prosper Exploration)
## by (Dieynaba Wane)


## Dataset

>Pour notre choix de dataset nous avons porté notre choix sur les données de prets de Prosper.
 cet ensemble de données contient 113 937 prêts avec 81 variables sur chaque prêt, y compris le montant du prêt, le taux de l'emprunteur (ou taux d'intérêt), le statut actuel du prêt, le revenu de l'emprunteur, et bien d'autres. 
Notre dataset est trop volumineux , elle contient 81 colonnes or toutes les colonnes ne seront pas forcément utiles pour nos recherches , de ce fait nous allons réduire les colonnes de notre dataset à 20 colonnes .
Aussi nous travaillerons avec une copie de notre dataset pour ne pas nuire à son intégrité .
**Voici la liste des colonnes que nous utliserons et leurs définitions**
><ol> 
    <li> ListingCreationDate :  La date à laquelle la liste a été créée. </li>
    <li> Term : La durée du prêt exprimée en mois.</li>
    <li> LoanStatus : L'état actuel du prêt : Annulé, Remboursé, Terminé, En cours, En défaut, Paiement final en cours, En souffrance. Le statut PastDue sera accompagné d'un seau de délinquance.</li>
    <li>ClosedDate : L'état actuel du prêt : Annulé, Remboursé, Terminé, En cours, En défaut, Paiement final en cours, En souffrance. Le statut PastDue sera accompagné d'un seau de délinquance.</li>
    <li>BorrowerAPR : Le taux annuel effectif global (TAEG) de l'emprunteur pour le prêt.</li>
    <li>LenderYield : Le prêteur rapporte le prêt. Le rendement du prêteur est égal au taux d'intérêt sur le prêt moins les frais de service.</li>
    <li>BorrowerRate : Le taux d'intérêt de l'Emprunteur pour ce prêt.</li> 
    <li>ProsperRating (numeric) : La note Prosper attribuée au moment de la création de l'annonce : 0 - N/A, 1 - HR, 2 - E, 3 - D, 4 - C, 5 - B, 6 - A, 7 - AA. Applicable aux prêts émis après juillet 2009.</li>
    <li>ProsperRating (Alpha) : La note Prosper attribuée au moment de la création de la liste entre AA et HR. Applicable aux prêts émis après juillet 2009.</li>
    <li>ProsperScore : Un score de risque personnalisé construit à l'aide des données historiques de Prosper. Le score varie de 1 à 10, 10 étant le meilleur score de risque ou le score de risque le plus faible. Applicable aux prêts émis après juillet 2009.</li>
    <li>BorrowerState : L'abréviation à deux lettres de l'état de l'adresse de l'emprunteur au moment de la création de l'annonce.</li>
    <li>Occupation : La profession sélectionnée par l'emprunteur au moment de la création de l'annonce.</li>
    <li>TotalProsperLoans :  Nombre de prêts Prosper accordés à l'emprunteur au moment où il a créé cette liste. Cette valeur sera nulle si l'emprunteur n'a pas eu de prêts antérieurs.</li>
    <li>AmountDelinquent : Dollars en souffrance au moment où le profil de crédit a été retiré.</li>
    <li>IncomeRange : La fourchette de revenus de l'emprunteur au moment de la création de l'annonce.</li>
    <li>MonthlyLoanPayment : La mensualité prévue du prêt. </li>
    <li>LoanOriginalAmount : Le montant initial du prêt.</li>
    <li>LP_ServiceFees : Frais de recouvrement cumulés payés par les investisseurs qui ont investi dans le prêt.</li>
    <li>LoanOriginationDate : La date à laquelle le prêt a été émis. </li>
    <li>Investors : Le nombre d'investisseurs qui ont financé le prêt. </li>
</ol>
>d'abord nous avons listé les nombres de valeurs nulles dans les variables puis supprimmé les lignes contenant les valeurs nulles dans nos variables ,ensuite renommons les variables ProsperRating (numeric) , ProsperRating (Alpha) pour moins d'encombrements , nous avons aussi converti ProsperRating(Alpha) ,IncomeRange en types de données catégoriques ordonnées , les variables ClosedDate , ListingCreationDate qui sont de type string en type date .

## Summary of Findings

> Dans l'exploration nous avons trouvé que que la distribution du montant d'origine du prêt est asymétrique à droite et j'ai effectué une transformation de journal dessus pour interpréter la visualisation.
L'année 2013 a enregistré la création de prêts la plus élevée. La Californie (CA) avait le plus grand nombre de prêts.
Aussi nous remarquons que les prêts  achevés ont un taux APR inférieur à celui des prêts en souffrance , les emprunteurs avec un prosper_rating égale **AA** moins nombreux ont un taux APR plus bas contrairement à ceux ayant un prosper_rating égale à **E** ou à **HR** qui ont des taux APR élevés,  qu'en général les emprunteurs habitant à **DE** : *Delaware* ont un taux d'APR beaucoup plus bas par rapport aux états  ; enfin les emprunteurs avec aucun revenu ou des revenus entre 1 et 24,999 achevés ont des taux APR supérieurs aux autres avec,pour des emprunteurs avec aucun revenu les taux APR minimum commencent à peu près  0.24.
Enfin , il est surprenant de savoir que quelque soit le statut du Loan,on remarque que le prosperRating joue un role essentielle sur le sur les taux d'intérets des prets plus plus prosperRating est bas plus le taux d'intérets est haut .
.
## Key Insights for Presentation

> Pour la présentation, je me concentre uniquement sur l'influence du BorrowerAPR sur les variables catégoriels LoanStatus et IncomeRange
D'abord  j'ai commencé par faire une matrice et tracé de corrélation entre les variables numériques pour voir les relations entre elles .
Ensuite pour voir la relation entre la variable numérique BorrowerAPR et la variable catégorielle LoanStatus j'ai effectué un ensemble de tracé , un diagramme à violon , un diagramme  de boites à moustaches et un diagramme de facettage pour avoir avoir un aperçu de la relation  des deux variables sous différents angles; ce meme procédé a été aussi utilisé pour voir les relations qui existent entre les variables numériques BorrowerAPR et  catégoriels IncomeRange. 