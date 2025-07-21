*(La version française suit)*

# Canadian Occupations in Qualtrics

This is an implementation of [select2](https://select2.org) designed to caputre occupations and [National Occupation Classification](https://noc.esdc.gc.ca) (NOC) Codes to be used in Canadian Public Opinion Research. A version of this implementation was included in the [2025 Canadian Election Study](http://www.ces-eec.ca/2025-canadian-election-study/) (CES) enabling a comparison of results from surveys to the CES.

You can preview this module in [English](https://wlu.yul1.qualtrics.com/jfe/preview/previewId/e3838849-4ee2-4cfd-ac56-39e3ac68396b/SV_74CArtrQmN7GGma?Q_CHL=preview&Q_SurveyVersionID=current) or [French](https://wlu.yul1.qualtrics.com/jfe/preview/previewId/0425bcf7-feba-4a98-ae55-0fac4a74ef90/SV_e2QMOhsHJbthrGC?Q_CHL=preview&Q_SurveyVersionID=current).

If you have any issues or concerns please pull an issue on this repository.

# Implementaiton in Qualtrics 

1. **Edit custom header to include the following code to implement select2:**

```
<!-- Select2 CSS -->
<link href="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/css/select2.min.css" rel="stylesheet" />
<!-- jQuery (required by Select2) -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<!-- Select2 JavaScript -->
<script src="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/js/select2.min.js"></script>

```

2. **Create a "Single line" "Text entry" question**
3. **Edit the JavaScript in for the "Text entry" question**
Paste the contents of [question_javascript](question_javascript) into the question JavaScript for the "Text entry" question. The occupation names and NOC codes are drawn from `occupations.js` Make sure to change **all** instances of `QID1` to the question ID for your occupation question in your survey.

To implement this method in French paste the code from [question_javascript_fr](question_javascript_fr) into your qualtrics Javascript. The occupation names and NOC codes for the French version are drawn from `occuptions_fr.js`. 

5. **_(Optional)_ Add a confirmation question following the occupation question**

We include a confirmation question following the occupation question to ensure that we have acurately captured an individual's occupation and industry. The confirmation question allows respondents to see the occupation category that they were placed in to ensure that it accurately reflects their occupation. It also enables them to enter another occupation if their occupation was not listed. 

```
You entered ${e://Field/occupation-name} which corresponds to ${e://Field/occupation-category}. Is this correct? 
If not go back to previous question. 

If your occupation was not listed please enter it below:
```

6. **Download Data**

Data from the occupation question will not appear in the default question responses in Qualtrics and will only appear in the embedded data on Qualtrics or when the data is downloaded. 

# Citiation 

If you publish results using this question please cite:

Campos-Gottardo, Rafael and Simon Kiss. (2025). "Recoding Occupations From the Canadian Election Study." Under Review in the *Canadian Journal of Political Science*.

---

# Professions Canadiennes dans Qualtrics

Ceci est une implémentation de [select2](https://select2.org) conçue pour recueillir les professions et les codes de la [Classification nationale des professions]([https://noc.esdc.gc.ca](https://noc.esdc.gc.ca)) (CNP), à utiliser dans la recherche sur l’opinion publique au Canada. Une version de cette implémentation a été incluse dans la [Étude électorale canadienne de 2025](http://www.ces-eec.ca/2025-canadian-election-study/) (EEC), permettant une comparaison entre les résultats des sondages et ceux de l’EEC.

Vous pouvez prévisualiser ce module en [anglais](https://wlu.yul1.qualtrics.com/jfe/preview/previewId/e3838849-4ee2-4cfd-ac56-39e3ac68396b/SV_74CArtrQmN7GGma?Q_CHL=preview&Q_SurveyVersionID=current) ou en [français](https://wlu.yul1.qualtrics.com/jfe/preview/previewId/0425bcf7-feba-4a98-ae55-0fac4a74ef90/SV_e2QMOhsHJbthrGC?Q_CHL=preview&Q_SurveyVersionID=current).

Si vous rencontrez des problèmes ou avez des questions, veuillez soumettre une *issue* sur ce dépôt.

# Implémentation dans Qualtrics

1. **Modifiez l’en-tête personnalisé pour inclure le code suivant afin d’activer select2 :**

```html
<!-- Select2 CSS -->
<link href="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/css/select2.min.css" rel="stylesheet" />
<!-- jQuery (requis par Select2) -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<!-- JavaScript Select2 -->
<script src="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/js/select2.min.js"></script>
```

2. **Créez une question de type "Entrée de texte" à ligne unique**
3. **Modifiez le JavaScript de la question "Entrée de texte"**
Collez le contenu de [question_javascript_fr](question_javascript_fr) dans le champ JavaScript de la question. Les noms de professions et les codes CNP sont tirés de `occupations_fr.js`. Assurez-vous de remplacer **toutes** les occurrences de `QID1` par l’ID de la question sur les professions dans votre sondage.

Pour utiliser la méthode en anglais, utilisez plutôt le code de [question_javascript](question_javascript), qui utilise `occupations.js`.

5. **_(Optionnel)_ Ajouter une question de confirmation après la question sur la profession**

Nous ajoutons une question de confirmation pour s’assurer que la profession et le secteur d’activité de l’individu ont été correctement identifiés. Cette question permet aux répondants de vérifier la catégorie professionnelle qui leur a été assignée et de la corriger au besoin. Elle leur donne aussi la possibilité d’entrer une profession différente si la leur n’apparaissait pas dans la liste.

```text
Vous avez entré ${e://Field/occupation-name}, qui correspond à ${e://Field/occupation-category}. Est-ce correct ?

 Si ce n'est pas le cas, revenez à la question précédente.

 Si votre profession ne figurait pas dans la liste, veuillez l'entrer ci-dessous :
```

6. **Téléchargement des données**

Les données recueillies par la question sur la profession n’apparaîtront pas dans les réponses par défaut de Qualtrics, mais uniquement dans les *données intégrées* ou lors du téléchargement des données.

# Citation

Si vous publiez des résultats basés sur cette question, veuillez citer :

Campos-Gottardo, Rafael et Simon Kiss. (2025). « Recodage des professions à partir de l’Étude électorale canadienne ». En évaluation dans la *Revue canadienne de science politique*.
