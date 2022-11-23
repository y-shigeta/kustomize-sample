# Kustomize

## install
brew install kustomize
kustomize version --short
kustomize completion bash >> ~/.bashrc

- 構成ファイルを作成する
mkdir -p base/
mkdir -p overlays/{prd,dev}/
touch base/deployment.yml
touch base/service.yml
touch base/kustomization.yml
touch overlays/{prd,dev}/deployment.yml
touch overlays/{prd,dev}/kustomization.yml

## Usage
- 適用済のManifestとOverlayを比較する
kubectl diff -k [overlaysのdirpath]
- 標準出力にManifestを表示
kustomize build [overlaysのdirpath]
- 標準出力に表示されたManifestをApply
kustomize build [overlaysのdirpath] | kubeclt apply -f -

