# Pangeo Notebook Veda Image

## Testing the image

The notebooks in `image-tests/` folder are used to test the docker image. They are run by `repo2docker` github action during the build process and the output is compared to the existing notebooks.

To add new tests, create new notebooks or add to the existing notebooks in `image-tests/` and generate the output of the notebooks by running the following command:

```bash
docker build -t pangeo-notebook-veda .
docker run -v image-tests:/home/jovyan/image-tests pangeo-notebook-veda jupyter nbconvert --to notebook --inplace --execute image-tests/*.ipynb
```