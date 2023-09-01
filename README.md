## Student Blog Site
Welcome to my personal blogging site! My name is Advik Garg and I am a Sophomore at Del Norte HS.
- This blogging site is built using GitHub Pages [GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site).
- The primary languages and frameworks that are used are `JavaScript/HTML/CSS`, `Python/Flask`, `Java/Spring`.  Read below for more details.
- This site has incorporated ideas and has radically modified scripts from the now deprecated [fastpages](https://github.com/fastai/fastpages) repository.
- This site includes assistance and guideance from ChatGPT, [chat.openai.com](https://chat.openai.com/) 

### Courses and Pathway
The focus of the Del Norte Computer Science three-year pathway is `Full Stack Web Development`.  This focus provides a variety of technologies and exposures.  The intention of the pathway is breadth and exposure.
- `JavaScript` documents are focused on frontend development and for entry class into the Del Norte Computer Science pathway.  JavaScript documents and materials are a prerequisites to Python and Java classes.
- `Python` documents are focused on backend development and requirements for the AP Computer Science Principles exam.
- `Java` documents are focused on backend development and requirements for the AP Computer Sciene A exam.
- `Data Structures` materials embedded into JavaScript, Python, or Java documents are focused on college course articulation.

### Resources and Instruction
- `Visual Studio Code` is key the code-build-debug cycle editor used in this course, [VSCode download](https://code.visualstudio.com/).  This is an example of a resource, but inside of it it has features for collaboration.

## GitHub Pages
All `GitHub Pages` websites are managed on GitHub infrastructure. GitHub uses `Jekyll` to tranform your content into static websites and blogs. Each time we change files in GitHub it initiates a GitHub Action that rebuilds and publishes the site with Jekyll.  
- GitHub Pages is powered by: [Jekyll](https://jekyllrb.com/).
- Published student website: [advikg.github.io/student](https://advikg.github.io/student/)

### WSL(Windows) and/or Ubuntu installation requirements
- The result of these step is Ubuntu tools to run preview server.  These procedures were created using [jekyllrb.com](https://jekyllrb.com/docs/installation/ubuntu/)
```bash
# 
# WSL/Ubuntu setup
#
mkdir mkdir vscode
git clone https://github.com/advikg/student.git
# run script, path vscode/student are baked in script
~/vscode/student/scripts/activate_ubuntu.sh
#=== !!!Start a new Terminal!!! ===
#=== Continue to next section ===
```

### MacOs installation requirements 
- Ihe result of these step are MacOS tools to run preview server.  These procedures were created using [jekyllrb.com](https://jekyllrb.com/docs/installation/macos/). 

```bash
# 
# MacOS setup
#
mkdir mkdir vscode
git clone https://github.com/advikg/student.git
# run script, path vscode/student are baked in script
~/vscode/student/scripts/activate_macos.sh
#=== !!!Start a new Terminal!!! ===
#=== Continue to next section ===
```


### Run Server On Local Machine:
- The result of these step is server running on: http://127.0.0.1:4200/student/.  Regeneration messages will run in terminal on any save and update site upon refresh.  Terminal is active, press the Enter or Return key in the terminal at any time to see prompt to enter commands.

- Complete installation
```bash
cd ~/vscode/student
bundle install
make
```
- Run Server.  This requires running terminal commands `make`, `make stop`, `make clean`, or `make convert` to manage the running server.  Logging of details will appear in terminal.   A `Makefile` has been created in project to support commands and start processes.

    - Start preview server in terminal
    ```bash
    cd ~/vscode/student  # my project location, adapt as necessary
    make
    ```

    - Terminal output of shows server address. Cmd or Ctl click http location to open preview server in browser. Example Server address message... 
    ```
    Server address: http://127.0.0.1:4200/student/
    ```

    - Save on ipynb or md activiates "regeneration". Refresh browser to see updates. Example terminal message...
    ```
    Regenerating: 1 file(s) changed at 2023-07-31 06:54:32
        _notebooks/2024-01-04-cockpit-setup.ipynb
    ```

    - Terminal message are generated from background processes.  Click return or enter to obtain prompt and use terminal as needed for other tasks.  Alway return to root of project `cd ~/vscode/student` for all "make" actions. 
        

    - Stop preview server, but leave constructed files in project for your review.
    ```bash
    make stop
    ```

    - Stop server and "clean" constructed files, best choice when renaming files to eliminate potential duplicates in constructed files.
    ```bash
    make clean
    ```

    - Test notebook conversions, best choice to see if IPYNB conversion is acting up.
    ```bash
    make convert
    ```
    