# public-adr
Public application definition repository, for adding public applications to a gitops tracked environment.

## Environments

There are currently to tracked environments: `/staging/` and `production`.
Prepared for `preview` environments but that is currently unused, and not sure it will be a gitops setup.

At the time of writing implicit `kustomization` is used through flux.
Meaning all files in each folder will be added to the cluster, they need to be valid `kubernetes` manifests (include `CRDs`).
Thus no base wich patches apples (as stated as good practice in flux demos).
Merging of files are currently offhanded to other pipelines which copies complete files to this repo.

That is the reason you migh find what appears to be "duplicate" files in the repo.
It is to help facilitate and copy resource from outside sources into the repo, without having to edit explicit kustomization files in the repo.

