# Teachbook Editor test in the TeachBooks template

The template allows you to test the TeachBook Editor: 

![image](https://github.com/user-attachments/assets/506238db-2ec7-4241-86d7-3ab20f14e799)

You can test this in your own book linked to a GitHub repository or use this template repository.

## Option 1: Test with your own book linked to a GitHub repository

1. Add the following lines to your requirements.txt:

```
--extra-index-url https://test.pypi.org/simple/
teachbooks_software_project_extension_name==0.1.3
```

2. Change the baseurl and repository_url properties in `book/_config.yml` under `html` and `html_theme_options` to `https://<your_username>.github.io/<your_repository_name>/` and `https://github.com/<your_username>/<your_repository_name>` respectively. The end result should look like this:

```yaml
html:
      favicon : "figures/TB_favicon.ico"                 # Replace this with your own favicon
      baseurl : "https://<your_username>.github.io/<your_repository_name>/"
...
html_theme_options:
      ...
      repository_url: "https://github.com/_<your_username>_/_<your_repository_name>_"
```

3. Add the extension `teachbooks_software_project_extension_name` to `book/_config.yml` under `sphinx - extra extensions`. The end result should look like this:

```yaml
sphinx:                                              # Options passed on to the underlying sphinx-parser
  extra_extensions:                                  # Gives you a starter package of extensions to use in your book
    ...
    - teachbooks_software_project_extension_name
```

4.  Now checkout the progress of the publishing workflow under `Actions` - `All workflows` -  `call-deploy-book` -`<the most recent workflow run>`. Remember, the first commit which is there has failed because GitHub Pages wasn't activated at the time of `Initial commit`.

5. When the workflow has finished, visit your built TeachBook at `https://<username or organiszation_name>.github.io/<repository_name>` (case sensitive). For our example it is [https://dummydocent.github.io/test_book_from_template/](https://dummydocent.github.io/test_book_from_template/) for the shown repository. These links are visible in the action's summary as well, as shown in the figure of step 4.

5. For creating the PAT, the user has to click the "Don't have an access token?" hypertext, which will redirect them to the GitHub page for creating a token. After that the user will have to write down the name of the token in the input box for Token name, change repository access to all repositories and go under permissions/repository permissions and change contents to read and write. When clicking Generate token, the user will be redirected to a page which displays the token. They have to copy and store that if they don't want to redo the token creation process again. After that is done, the user can input the token into the input box under "Enter GitHub Access Token", which would allow them access to the rest of the GitHub functionality.

7. To test the TeachBooks editor, click the 'edit page' button on the top of a page in your built book

## Option 2: Test with this template book repository

How to use the template is demonstrated in the figure below, all steps are elaborated on in the following step-by-step tutorial.

1. To get started, use the [template TeachBook](https://github.com/TeachBooks/main/template) as template:

![Use template](https://github.com/TeachBooks/template_figures/blob/main/use_template.png?raw=true)

2. Fill in a repository name, this name will be used in the future url of your book:

![Create new repository](https://github.com/TeachBooks/template_figures/blob/main/create_new_repository.png?raw=true)

3. You need to activate GitHub pages so that your website is published to the internet. As long as you don't do this your TeachBook is not published online. Actually, now that you've taken this template our workflow tries to publish it to GitHub pages, which you didn't have the chance to activate yet. That's why you probably received an email with 'call-deploy-book: Some jobs were not successful' and you see the failed job under `Initial commit`. You can activate GitHub pages by setting the source for GitHub pages to GitHub Actions under `Settings` - `Pages` - `Build and deployment` - `Source` - `GitHub Actions`:

![Activate GitHub Pages](https://github.com/TeachBooks/template_figures/blob/main/set_up_pages.png?raw=true)

4. Change the baseurl and repository_url properties in `book/_config.yml` under `html` and `html_theme_options` to `https://<your_username>.github.io/<your_repository_name>/` and `https://github.com/<your_username>/<your_repository_name>` respectively. The end result should look like this:

```yaml
html:
      favicon : "figures/TB_favicon.ico"                 # Replace this with your own favicon
      baseurl : "https://<your_username>.github.io/<your_repository_name>/"
...
html_theme_options:
      ...
      repository_url: "https://github.com/_<your_username>_/_<your_repository_name>_"
```

5.  Now checkout the progress of the publishing workflow under `Actions` - `All workflows` -  `call-deploy-book` -`<the most recent workflow run>`. Remember, the first commit which is there has failed because GitHub Pages wasn't activated at the time of `Initial commit`.

6. When the workflow has finished, visit your built TeachBook at `https://<username or organiszation_name>.github.io/<repository_name>` (case sensitive). For our example it is [https://dummydocent.github.io/test_book_from_template/](https://dummydocent.github.io/test_book_from_template/) for the shown repository. These links are visible in the action's summary as well, as shown in the figure of step 3.

7. For creating the PAT, the user has to click the "Don't have an access token?" hypertext, which will redirect them to the GitHub page for creating a token. After that the user will have to write down the name of the token in the input box for Token name, change repository access to all repositories and go under permissions/repository permissions and change contents to read and write. When clicking Generate token, the user will be redirected to a page which displays the token. They have to copy and store that if they don't want to redo the token creation process again. After that is done, the user can input the token into the input box under "Enter GitHub Access Token", which would allow them access to the rest of the GitHub functionality.

8. To test the TeachBooks editor, click the 'edit page' button on the top of a page in your built book
