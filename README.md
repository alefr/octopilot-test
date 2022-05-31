# public-adr
Public application definition repository, for adding public applications to a gitops tracked environment.

## Environments

There are currently two tracked environments: `/staging` and `/production`.
The repo is prepared for preview enviroments, but but that is currently unused, and not sure if it will be a gitops setup (or at least through this repo).

At the time of writing implicit `kustomization` is used through flux.
Meaning all files in each folder will be added to the cluster, they need to be valid `kubernetes` manifests (include `CRDs`).
Thus there's no base with corresponding patches for each environment (as stated as good practice in flux demos).
Merging of files are currently offhanded to other pipelines which copies complete files to this repo.

That is the reason you migh find what appears to be "duplicate" files in the repo.
It is to help facilitate and copy resource from outside sources into the repo, without having to edit explicit kustomization files in the repo.

