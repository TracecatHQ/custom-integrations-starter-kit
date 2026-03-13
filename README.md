# Tracecat Starter Kit

Click on `Use this template` to copy Tracecat's custom integrations starter kit.
Then check out the [custom registry installation docs](https://docs.tracecat.com/tutorials/custom-integrations).


This starter kit contains:
- `pyproject.toml` config file
- Example Python UDFs (user defined functions) in `mapping.py` and `greetings.py`
- An example Action Template in `custom_actions/templates/power_of_three.yml`.

**Note:**
- When setting your git URL, the correct scheme is: `git+ssh://git@github.com/<username>/<repo>.git` (notice the "/<username>" not ":<username>")
- You can safely delete example Python integrations files and templates under `custom_actions/`
- **Do not** remove `pyproject.toml`. This is required for your Tracecat instance to install and run your custom integrations.
- You can add 3rd party `pip` packages (e.g. `psycopg==3.2.4`) in the `pyproject.toml` file under [`project.dependencies` here](https://github.com/TracecatHQ/custom-integrations-starter-kit/blob/main/pyproject.toml#L11).
- The `dev` dependencies [line](https://github.com/TracecatHQ/custom-integrations-starter-kit/blob/main/pyproject.toml#L26) in `pyproject.toml` installs the `tracecat_registry` package. This allows you to test your Python functions locally and also enables linting.

### Renaming the package
If you want to rename `custom_actions` to `<your_registry_name>`, you must:
- Pick a package name that is in snakecase
- Rename the `custom_actions` directory to `<your_registry_name>`
- Change every `custom_actions` directory name in `pyproject.toml` to `<your_registry_name>`   

For example:

```bash
cd custom-integrations-starter-kit
mv custom_actions my_custom_integrations
sed -i 's/custom_actions/my_custom_integrations/g' pyproject.toml
``` 
