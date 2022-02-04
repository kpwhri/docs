
# Backend for `kpwhri.github.io`

## About

This project uses the sphinx static site generator to build markdown files into the website visible at https://kpwhri.github.io.

Any push to the `main` branch will automatically trigger a Github Action which will rebuild the website.

### Sphinx and Markdown

Sphinx is a powerful static site generator, but uses ReSTructured Text files rather Markdown. This project therefore relies on
 [MyST](https://myst-parser.readthedocs.io/en/latest/index.html) to handle the Markdown parsing. The interoperability is not
 perfect and many sphinx directives must be called within a markdown codeblock in restructured text format.

## Contributing

### Prerequisites

* Git
* Python 3.9+
  * `sphinx` and other packages specified in `requirements.txt`

### Setup

* Clone project: 
  * `git clone https://github.com/kpwhri/kpwhri.github.io`
  * `cd kpwhri.github.io`
* Create/activate virtual environment
  * `python -m venv .venv`
  * `.venv\Scripts\activate.ps1` or `source .venv/bin/activate`
* Install requirements
  * `pip install -r requirements.txt`
* Start up live reload server so you can test changes locally
  * `cd docs`
  * `python run_livereload.py`
  * Open browser to `http://127.0.0.1:5500`

### Making Contributions

This will cover some very basic operations, and for more interesting options and formatting, look at [MyST documentation](https://myst-parser.readthedocs.io/en/latest/index.html)
 and [Sphinx documentation](https://www.sphinx-doc.org/en/master/).

After making any changes, please:
1. Test your changes on the live reload server.
2. Add any changes (`git add my_cool_thing.md`)
3. Commit your code (`git commit -am "Added new page describing sentinel work"`)
4. Push your changes (`git push origin main`)

#### Create a New Page

* In the `docs` directory, create a new markdown file (e.g., `my_cool_thing.md`).
* Create a title (this will be automatically used for internal linking): `# My Cool Thing`
* Organize the content into sections around headings:
```markdown
# My Cool Thing

## Motivation
We needed something cool included in this project.

## Implementation Details
This will create a bulleted list:
* Design with design team
* Data wrangling with data wrangling team
* Analytics with analytic team
  * This is a sub-bullet

## Future Roadmap

1. Type `1.` and keep writing.
2. This is the second item in the enumerated list.
```

#### Add Callout/Info Box

Ensure that this example is left-justified (no indentation).

    ```{admonition} Avoid Internet Hazards
    All hazards are best avoided.
    ```

#### Code Snippet

Include a code snippet by typing including it within backticks.

Specify the language or file format:

    ```sas
    proc sql;
        select * from everwhere;
    quit;
    ```

    ```python
    print(42)
    ```

    ```json
    {
        "is_json": true,
    }
    ```

#### Add An Image

1. Download the image to your computer.
2. Add the image to the `docs/images` directory with a useful name.
3. Reference the image like `![](images/my-cool-thing.png)`.
4. Ensure that the image is add to the commit.
