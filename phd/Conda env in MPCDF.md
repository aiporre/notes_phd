#mpcdf
#clustermpi
# anaconda
The steps:
1. set the channels from default to forge-conda
2. use the waterboa
3. you need to create a container that has your `requirements.yaml` 
4. set the document and the intallation command i.e. `conda install -f requirements.yaml`
# conda tips
1. yo need t ubunt-base apptainer container to avoid error GLIBC_2.33 not found
2. Avound rc files avoid `conda init`
3. runing `source activate` should be better.
4. mamba and conda are available.
5. Avoid MPI from conda-forge 
6. IF applicable remember to clear the directory $HOME/conda-envs
7.  --bind /u:/u, /ptmp:ptmp is applied to allow to solve the directory.
# summary
1. condainer putr conda env into compre (squshfs) image with out the over lo of requiring a bas os image
2. caprpentires-icuaper .gth.io/introduction-to-conda-for-data-scientist
