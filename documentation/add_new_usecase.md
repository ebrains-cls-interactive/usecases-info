
# Add new use case in an existing category

The structure of [usecases-info.json](../usecases-info.json) is the following:
```
[
   {
      "title": "Trace Analysis", # category name
      "id": "traceanalysis", # category id
      "usecases": [<USECASE_INFORMATION>], # list of use cases for this category
   },
]
```

## Use case information (USECASE_INFORMATION)
```
{
   "id": id of the item,
   "title": title of the usecase,
   "description": description of the usecase,
   "experience": [<experience_choice>],
   "maturity":  [<maturity_choice>],
   "access": [<access_choice>],
   "disabled": boolean if the usecases is accessible or not,
   "contributors": [<contributor_info>],
   "picture": {
      "src": url of the image,
      "alt": description of the image (for accessibility)
   },
   "dataProtected": if the user should accept terms and conditions [true, false]
   "implementation": <implementation_choice>,
   "notebookRepoUrl": (if 'implementation' == 'ipynb') repo where the notebooks are located,
   "notebookPath": (if 'implementation' == 'ipynb') relative path to the notebook,
   "tutorial": url of video tutorial,
   "externalUrl": (if 'implementation' == 'webapp') link to the web app,
   "chooseModel": boolean value if choosing a model is required for the use case,
   "externalUrlModelPlaceholder": (if 'chooseModel' == true) string to be used for replacing values "{EXTERNAL_URL}/?model={MORPHOLOGY_URL}",
   "maxModelSelection": number of maximum models that can be selected,
},
```

## Explanation of some of the values:

* #### experience_choice:
   * `"all"` ("Everybody") - "Easily accessible use case"
   * `"power"` ("Power users") - "Advanced use case"
   * `"experts"` ("Experts") - "Use case for contributors and tools experts"
   * `"code"` ("Developers") - "Use case for tools developers"

* #### maturity_choice:
   * `"beta"` ("Beta") - A service of this maturity level has reached a certain robustness and may be used by early adopters.
   * `"experimental"` ("Experimental") - A service of this maturity level is under heavy development and recommended only for specialists’ use or use for co-design partners.

* #### access_choice:
   * `"hpc"` ("HPC") - Requires high-performance computing resources access
   * `"byor"` ("BYOR") - (Bring Your Own Resources) Services of this type allow you to delegate the execution to resources provided by the user. This is subject to technical compatibility.

* #### implementation_choice:
   * `"ipynb"` Jupyter notebook
   * `"webapp"` Web application

* #### contributor_info:
   * `{"name": <string>, "email": <string>}`


# Add a new Category

Like (Trace analysis, Morphology, Circuit building, etc)
Create a new top level entry into the usecases-info.json:
```
[
   {
      "title": "Trace Analysis",
      "id": "traceanalysis",
      "usecases": [<USECASE_INFORMATION>],
   },
   ...
   {
      "title": "YOUR_NEW_CATEGORY_TITLE",
      "id": "YOUR_NEW_CATEGORY_ID",
      "usecases": [<USECASE_INFORMATION>],
   },
]
```
Remember that `YOUR_NEW_CATEGORY_ID` should be in lowercase and no spaces.
