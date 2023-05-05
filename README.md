# minimal-jupyter-notebook-devspace

A minimal jupyter notebook `devspace.yaml` with `openai` + `langchain` allow you to work on any Kubernetes cluster.

## Deploy

Build images and deploy a jupyter notebook in Kubernetes namespace `ai`

```bash
devspace use namespace ai
devspace deploy --max-concurrent-builds=2 # use this on Intel Mac
```

## Start

```bash
devspace dev
```

`.ipynb` files in `notebooks` will be synced to the `jupyter-notebook` container, edit files in <[http](http://localhost:8888/lab)> would sync back to local.

## Clean up

Delete all deployments

```bash
devspace purge
```

## Reset

Revert the container back to the state when we `devspace deploy`

```bash
devspace run-pipeline stop-dev
```

## Remove notebook output

```bash
brew install jupyter
```

Set config for this repo once (see `.gitattributes`)

```bash
git config filter.strip-notebook-output.clean 'jupyter nbconvert --ClearOutputPreprocessor.enabled=True --to=notebook --stdin --stdout --log-level=ERROR'  
```
