# flygastrula2
This is the GitHub page for the "Single-cell transcriptome atlas of Drosophila gastrula 2.0" (Sakaguchi et al., 2021, bioRxiv) [\[link\]](https://www.biorxiv.org/content/10.1101/2021.12.27.474293v1). The paper describes the data obtained from single-cell RNA sequencing of the Drosophila gastrula.

All processed data including UMI count tables, Seurat objects and loom files are available are available [here](https://kyotouac-my.sharepoint.com/:f:/g/personal/kondo_takefumi_7v_kyoto-u_ac_jp/Em050jK6biJPp5spAcPqFqMBxEesA0gM5U0I4pNBzrnRXQ?e=u4l1gU).

Loom files are compatible with viewing in [SCope](https://scope.aertslab.org).　　

Jupyter Notebooks used for data analysis are also available on this page.

The viewer, described below, allows browsing the dataset, including cluster information and gene expression level on UMAP, the gene expression level in each pair-rule stripe, and spatial gene expression reconstructed by Perler and NovoSpaRc on the browser.

## How to use the Viewer

<img src="./sample_movie_20230306_trimmed.gif" width = 800>

The viewer environment is built using Docker, and the installation process is as follows.

### Docker install

If you have not yet installed Docker, install [Docker desktop](https://docs.docker.com/engine/install/)

### Download our viewer

Download our viewer source from [here](https://kyotouac-my.sharepoint.com/:f:/g/personal/kondo_takefumi_7v_kyoto-u_ac_jp/EiChKaXMm5BKghVDLpVTnR8BYGaPtvughljkGcn0lnSQNQ?e=8yHygt)

### Run the viewer
 1. Start Docker desktop

 2. Start Terminal and move to the directory of the viewer source:
```
cd flygastrula2_viewer #If the “flygastrula2_viewer” directory exists in the home directory.
```

3. Make the Docker image and container using Docker-compose:

```
docker-compose up -d --build
```

4. Run the viewer:

```
docker exec dmel-gastrula python app.py
```

Access [http://localhost:8050/](http://localhost:8050/) in your browser.

If "Single cell transcriptome atlas of *Drosophila* gastrula" is displayed on the top page, it is working.

You can brows our data on your browser.

Now, you can browse the Set3-CAP data including:
- Cluster information and gene expression level on UMAP (Seurat clusters, Sub-clusters, Genes)
- Gene expression level in each pair rule strip (Stripe)
- Spatial gene expression reconstructed by Perler and NovoSpaRc (VISH and Dual VISH)



Chrome or Safari on Mac is recommended for browsing. We have not tested our viewer on other Operation systems or browsers.

### Stop and restart the viewer
You can stop the Docker container with the following command in Terminal:
```
docker stop dmel-gastrula
```

If you want to restart the viewer, run the following command.
```
docker restart dmel-gastrula && docker exec dmel-gastrula python app.py
```
