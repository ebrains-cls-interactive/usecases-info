# Add a new Category

(optional) Like (Trace analysis, Morphology, Circuit building, etc)
Create a new entry (json) to the usecases.json (src/assets/config_files):
```
[
   {
      "title": "Trace Analysis",
      "id": "traceanalysis",
      "usecases": [<USECASE_INFORMATION>],
   },
   ...
   {
      "title": "YOUR_NEW_DOMAIN_TITLE",
      "id": "YOUR_NEW_DOMAIN_ID",
      "usecases": [<USECASE_INFORMATION>],
   },
]
```
Remember that `YOUR_NEW_DOMAIN_ID` should be in lowercase and no spaces.

# Add new Usecase in an existing domain

## Add the Usecase information (USECASE_INFORMATION)
Create a new entry (json) to the [usecases-info.json](usecases-info.json) inside an existing category with the following information:
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
   {"name": "...", "email": "..."},

* #### file_usecase:
   This array will contain the apps or files that they are going to be copied to the new Collab. The format should be something like
   ```
   {
      "entryname": name to be added in the navigation item when the usecase is created/added ,
      "appid": (number) possible values [175 (ipython notebboks), 6 (external html)],
      "contenttype": (string) possible values ["x-ipynb+json", "text/html"],
      "extension": (string) extension with "." like ".ipynb",
      "file": UUID of the file in collab storage (more information see below) OR raw file URL,
      "justcopy": (boolean) if true, it will avoid creating a nav item,
   }
   ```
* #### model_item:
  ```
  {
    "title": (string) title of the model
    "modelName": (string) text that is going to replace the placeholder in the notebook,
    "description": (string) description of the model,
    "contributors": [
      {
        "name": name of the contributor,
        "email": email of the contributor
      }
    ],
    "img": (url) link to the image for that model
  }
  ```

##### To get the raw file url
For example in github just look for the file and click on the button to visualize it RAW and copy that URL to the "file" attribute
 
##### To get the UUID in collab
* Go to the collab storage where the file is located.
* Click on the file and the URL bar will change from something like:
    `https://collab.humanbrainproject.eu/#/collab/<collab_number>/nav/<nav_number>"`
    to
    `https://collab.humanbrainproject.eu/#/collab/<collab_number>/nav/<nav_number>?state=uuid%3D915417d1-359f-4eab-bcb1-a0881dea8d7d`
    so now we have to take the last part `after` "state=uuid%3D" from the URL. Like:
    `915417d1-359f-4eab-bcb1-a0881dea8d7d`

# Add to the collab
If you added a uc inside an existing domain the usecase should appear in the list.
If you created a new domain you just need to pull request the changes in the usecases.json and then create a new Markdown item in the collab with the link of the domain name. 
Example: https://bbp.epfl.ch/public/usecases-wizard/index.html#/your_new_domain
