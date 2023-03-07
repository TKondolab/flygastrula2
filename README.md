# flygastrula2
The single-cell transcriptome atlas of *Drosophila* gastrula

This is the Github page for

"Single-cell transcriptome atlas of Drosophila gastrula 2.0" (S. Sakaguchi et al., 2021, bioRxiv)
[link](https://www.biorxiv.org/content/10.1101/2021.12.27.474293v1)

Jupyter notebooks for our analysis are available in this page.

## Data and the viewer are available

Our data and viewer for our data are available [here](http://example.com)

See description below if you want to use our viewer.

### Download our viewer

Download our viewer folder from [here](http://example.com)

### Docker install

The environment for our viewer is built using Docker. If Docker is not installed in your devise, install [Docker desktop](https://docs.docker.com/engine/install/)

### Run the viewer

On your terminal, move to top of viewer directory.
```
cd flygastrula2_viewer
```

Make the Docker image and container using Docker-compose

```
docker-compose up -d --build  
```

Run the viewer with the following command

```
docker exec dmel-gastrula python app.py
```

Access [http://localhost:8050/](http://localhost:8050/) in your browser.

If "Single cell transcriptome atlas of *Drosophila* gastrula" is displayed on the top page, it is working.  
You can brows our data on your browser.

![viewer image](./viewer.png)

For the browser, Chrome or Safari on Mac is recommended. We have not tested our viewer on other Operation systems or browsers.

### Stop and restart the viewer
You can stop the Docker container with the following command.
```
docker stop dmel-gastrula
```

If you want to restart the viewer, run the following command.
```
docker restart dmel-gastrula && docker exec dmel-gastrula python app.py
```
