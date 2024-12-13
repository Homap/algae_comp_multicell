mkdir -p .conda_algae_multicell/envs .conda_algae_multicell/pkgs
export CONDA_ENVS_PATH=./.conda_algae_multicell/envs
export CONDA_PKGS_DIRS=./.conda_algae_multicell/pkgs
mamba env create --file config/conda_env.yaml
# Install snakemake
mamba install -n ostrich_rec_mut -c conda-forge -c bioconda snakemake=8.20
mamba install -c bioconda snakemake-executor-plugin-slurm
mamba install -c bioconda snakemake-executor-plugin-cluster-generic
