# ReinfyTeam documentation

[![Documentation status](https://readthedocs.org/projects/reinfyteam-documentary/badge/?version=latest)](https://docs.reinfy.tk/)

Documentary is the public Sphinx documentation site for projects maintained by ReinfyTeam. The published site is available at [docs.reinfy.tk](https://docs.reinfy.tk/).

## Documentation structure

- `docs/conf.py` contains the Sphinx project configuration and Read the Docs entry point.
- `docs/index.rst` is the landing page and toctree for project guides.
- `docs/requirements.txt` contains the documentation-only Python dependencies.
- `.readthedocs.yaml` defines the hosted build, HTML output and PDF output.

The current landing page is intentionally small; project-specific guides can be added as reStructuredText pages and linked from `docs/index.rst`. Keep examples aligned with the current behavior of the corresponding ReinfyTeam project, and link to the authoritative repository or release documentation when a guide depends on a specific version.

## Local preview

Use a disposable Python environment so documentation dependencies do not mix with a project runtime:

```text
python -m venv .venv
.venv\Scripts\activate
python -m pip install -r docs/requirements.txt
sphinx-build -b html docs docs/_build/html
```

Open `docs/_build/html/index.html` after the build completes. The hosted configuration also requests a PDF output; a local HTML preview does not by itself verify the hosted PDF build.

## Contributing

Update the relevant reStructuredText page, add it to the `docs/index.rst` toctree, and keep the Sphinx configuration and examples consistent with the current project behavior. Do not commit the virtual environment or generated `docs/_build/` output.

## License

This documentation is released under the [GNU Lesser General Public License v2.1](LICENSE).
