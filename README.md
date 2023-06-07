# flygastrula2
This is the GitHub page for the "Single-cell transcriptome atlas of Drosophila gastrula 2.0" (Sakaguchi et al., 2023).

Processed data including UMI count tables, Seurat objects and loom files are available [here](http://dx.doi.org/10.17632/k8g638cmxv.1).<br>
Loom files are compatible with viewing in [SCope](https://scope.aertslab.org).<br>
Jupyter Notebooks used for data analysis are also available on this page.<br>
<br>
The viewer, described below, allows browsing the dataset, including cluster information and gene expression level on UMAP, the gene expression level in each pair-rule stripe, and spatial gene expression reconstructed by Perler and NovoSpaRc on the browser.
<br>
<br>

## How to use the Viewer
The viewer environment is built using Docker, and the installation process is as follows.
<img src="./sample_movie_20230306_trimmed.gif" width = 800>
<br>
<br>

### Docker install

If you have not yet installed Docker, install [Docker desktop](https://docs.docker.com/engine/install/)<br>
<br>
<br>

### Download the Docker image of the viewer 

Download "viewer.tar.gz" containing the Docker images of viewer from [here](http://dx.doi.org/10.17632/k8g638cmxv.1).<br>
<br>
<br>

### Run the viewer

1. Choose the arm64/amd64 flygastrula2_viewer.tar depending on your device, and move it to your home directory.<br>
2. Start Docker desktop<br>
3. Start Terminal, move to the home directory, and load the image into Docker by the following command.<br>
```
docker load -i flygastrula2_viewer.tar
```

4. Make the container by the following command.<br>
```
docker run -it -p 8050:8050 --name flygastrula2_viewer -w /home/ flygastrula2_viewer python app.py
```

5. When the display shows "Dash is running on http://0.0.0.0:8050/",<br>
   access [http://0.0.0.0:8050/](http://0.0.0.0:8050/) in your browser.<br>
<br>

  - For the browser, Chrome is recommended. 

  - Now, you can browse the Set3-CAP data, including
    - Cluster information and gene expression level on UMAP (Seurat clusters, Sub-clusters, Genes)
    - Gene expression level in each pair rule strip (Stripe)
    - Spatial gene expression reconstructed by Perler and NovoSpaRc (VISH and Dual VISH)
<br>

### Stop the viewer
6. You can stop the Docker container with the following commands in Terminal.
```
Control + P + Q
```

```
docker stop flygastrula2_viewer
```

```
docker rm flygastrula2_viewer
```

7. If you want to start again, please start from 4.
