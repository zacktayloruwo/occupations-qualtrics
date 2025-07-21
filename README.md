# Canadian Occupations in Qualtrics

This is an implementation of [select2](https://select2.org) designed to caputre occupations and [National Occupation Classification](https://noc.esdc.gc.ca) (NOC) Codes to be used in Canadian Public Opinion Research. A version of this implementation was included in the [2025 Canadian Election Study](http://www.ces-eec.ca/2025-canadian-election-study/) (CES) enabling a comparison of results from surveys to the CES.

# Implenmentaiton in Qualtrics 

1. Edit custom header to include the following code to implement select2:

```
<!-- Select2 CSS -->
<link href="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/css/select2.min.css" rel="stylesheet" />
<!-- jQuery (required by Select2) -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<!-- Select2 JavaScript -->
<script src="https://cdn.jsdelivr.net/npm/select2@4.1.0-beta.1/dist/js/select2.min.js"></script>

```

2. Create a "Single line" "Text entry" question
3. Edit the JavaScript in for the "Text entry" question
Paste the contents of file into the question JavaScript for the "Text entry" question. The occupation names and NOC codes are drawn from `occupations.js` Make sure to change **all** instances of `QID1` to the question ID for your occupation question in your survey.

To implement this method in French paste the code from occua_fr into your qualtrics Javascript. The occupation names and NOC codes for the French version are drawn from `occuptions_fr.js`. 

5. (Optional) Add a confirmation question following the occupation question

We include a confirmation question following the occupation question to ensure that we have acurately captured an individual's occupation and industry. The confirmation question allows respondents to see the occupation category that they were placed in to ensure that it accurately reflects their occupation. It also enables them to enter another occupation if their occupation was not listed. 

```
You entered ${e://Field/occupation-name} which corresponds to ${e://Field/occupation-category}. Is this correct? 
If not go back to previous question. 

If your occupation was not listed please enter it below:
```

6. Download Data

Data from the occupation question will not appear in the default question responses in Qualtrics and will only appear in the embedded data on Qualtrics or when the data is downloaded. 

# Citiation 

If you publish results using this question please cite:

Campos-Gottardo, Rafael and Simon Kiss. (2025). "Recoding Occupations From the Canadian Election Study." Under Review in the *Canadian Journal of Political Science*.

---

