# Manim Workspace Template

<a href="https://pypi.org/project/manim/"><img alt="pypi-version" src="https://img.shields.io/pypi/v/manim?logo=pypi&label=manim" /></a>
<a href="https://github.com/ManimCommunity/manim"><img alt="manim-gh-repo" src= "https://img.shields.io/badge/ManimCommunity-manim-blue?logo=github&logoColor=181717&color=red"></a>
[![CodeQL](https://github.com/kurodaritsu/manim-workspace/actions/workflows/github-code-scanning/codeql/badge.svg)](https://github.com/kurodaritsu/manim-workspace/actions/workflows/github-code-scanning/codeql)

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/kurodaritsu/manim-workspace?quickstart=1)

For `manim` animators who doesn't want to install package managers and dependencies (e.g. FFmpeg, LaTeX) in their local machine to have a working `manim` environment.

This workspace utilizes Dev Containers that handle `manim` installation, dependencies, and updates. The container uses `manim` [Docker image](https://hub.docker.com/r/manimcommunity/manim/tags).

With this template, you only need to install [VS Code](https://code.visualstudio.com/download) and [Docker](https://www.docker.com/get-started/) (if working locally) to use `manim`

This Dev Container also comes with FFmpeg and LaTeX for rendering Math text and [Manim Sideview](https://github.com/Rickaym/manim-sideview) VS Code Extension. For details on using the extension, visit the [extension page](https://marketplace.visualstudio.com/items?itemName=Rickaym.manim-sideview).

You can also use this container to run manim on JupyterLab. For details, see [Using the Workspace - Jupyter Lab](#jupyter-lab)


<a href="https://github.com/KaidenFrizu/manim-workspace/discussions"><img alt="I have a question" src="https://img.shields.io/badge/I_have_a_question-blue?style=for-the-badge&"></a>
<a href="https://github.com/KaidenFrizu/manim-workspace/issues"><img alt="I have an issue" src="https://img.shields.io/badge/I_have_an_issue-red?style=for-the-badge&"></a>


---

## Setup :gear:
### GitHub Codespaces
If you want to immediately start working on a project on a cloud environment using only your installed VS Code, try going through these steps below.

1. Open this repository in a codespace:

   ![](.github/md-resources/open_in_codespace.png)



2. Create a `manim` [Scene](src/example_scene.py), and enjoy working on your environment

> [!NOTE]
> Using Codespaces would consume Codespace Credits on your accounts. To learn more about Codespaces, visit [What are GitHub Codespaces - Billing for Codespaces](https://docs.github.com/en/codespaces/about-codespaces/what-are-codespaces#billing-for-codespaces)

> [!TIP]
> To re-open your existing codespace when you launch VS Code again, open a Command Palette (`F1` / `Ctrl + Shift + P` / `Cmd + Shift + P`), search for `Codespaces: Connect to Codespace...`, and select your existing codespace
>
> ![alt text](.github/md-resources/connect_to_codespace.png)

### Dev Containers

If you wanted to work on a project locally without consuming credits, you can go through these steps to have an isolated local environment.

> [!IMPORTANT]
> You must have [Docker](https://www.docker.com/get-started/) and [Visual Studio Code](https://code.visualstudio.com/download) with [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension installed

1. Create your own repository from this template.

   ![Repository Template](.github/md-resources/repo_template.png)

2. Clone or Download your created repository.

   ```
   git clone https://github.com/{YOUR_GH_USERNAME}/{YOUR_REPO_NAME}.git
   ```

   ![Clone or Download](.github/md-resources/download_repo.png)

3. In VS Code, Open the Command Palette (`F1` / `Ctrl + Shift + P` / `Cmd + Shift + P`)
4. Search and select `Dev Containers: Open Folder in Container...`

   ![Type Dev Containers](.github/md-resources/open_folder_in_container.png)

5. Select the folder that was cloned or downloaded to your computer.
6. When the setup if finished, create a `manim` [Scene](src/example_scene.py) and enjoy working on your environment.

> [!NOTE]
> If you've downloaded the repository, make sure to extract the contents in your `.zip` file before opening in the container.

> [!TIP]
> To re-open the container when you launch VS Code again, follow Steps 3-6

---

## Using the Container :desktop_computer:
You can use one (or both) methods to create and render animations in `manim`, depending on your preference.

### Manim Sideview

1. Open up a [Scene](src/example_scene.py) in your Dev Container Environment.
2. Open the Command Palette (`F1` / `Ctrl + Shift + P` / `Cmd + Shift + P`) and look for *"Manim: Render a New Scene"*
3. Select the scene from your current file that you wanted to render.
4. The output file would be autoplayed on the right side of your VS Code window.

   <img alt = "Manim Sideview Snapshot" src=".github/md-resources/manim_sideview_snapshot.png" style="width:75%; height:auto;">

> [!TIP]
> You can modify your settings in VS Code to automatically render the current scene on saving the `.py` file.
> ![manim-sideview.runOnSave](.github/md-resources/run_on_save_snapshot.png)

> [!TIP]
> For more details on how to use Manim Sideview, visit [Manim Sideview repository](https://github.com/Rickaym/Manim-Sideview)

### Jupyter Lab

1. In your Dev Container environment, open a terminal (`` Ctrl + ` ``).
2. Run the command `jupyter lab`.
3. Open one of the `http://` URLs given in the terminal to your browser.

   ![Jupyter URL to copy](.github/md-resources/jupyter_url_to_copy.png)

4. From the Jupyter Lab environment, create a [notebook](src/example_notebook.ipynb) and enjoy creating animations from here.

   <img alt = "Jupyter Manim Snapshot" src=".github/md-resources/jupyter_run_manim_snapshot.png" style="width:75%; height:auto;">

> [!TIP]
> To shutdown your current Jupyter Lab server, press `Ctrl + C` on the same terminal, or go to `File -> Shut Down` in Jupyter Lab window. To view currently running servers, run `jupyter server list` on a terminal.

> [!TIP]
> For more examples using `manim` on notebooks, visit:
> https://github.com/ManimCommunity/jupyter_examples
