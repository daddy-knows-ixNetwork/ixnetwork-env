# ixnetwork-env
ixnetwork script development environment for HLAPI and ixnetwork-restpy, snappi, snappi-ixnetwork

# how to build and run

## Build
```
seunyang@1H8618406V:~/support/daddy-knows-ixNetwork/ixnetwork-env$ docker compose build
[+] Building 1.5s (25/25) FINISHED                                                                       
 => [internal] load local bake definitions                                                          0.0s
 => => reading from stdin 1.84kB                                                                    0.0s
 => [ixnetwork26_5 internal] load build definition from Dockerfile                                  0.0s
 => => transferring dockerfile: 5.67kB                                                              0.0s
 => [ixnetwork internal] load metadata for docker.io/library/ubuntu:24.04                           0.4s
 => [ixnetwork26_0 internal] load .dockerignore                                                     0.0s
 => => transferring context: 2B                                                                     0.0s
 => [ixnetwork26_5  1/14] FROM docker.io/library/ubuntu:24.04@sha256:33ceb71981b602c1a7443a53469e4  0.0s
 => => resolve docker.io/library/ubuntu:24.04@sha256:33ceb71981b602c1a7443a53469e4dba065f7503eab30  0.0s
 => [ixnetwork26_5 internal] load build context                                                     0.0s
 => => transferring context: 110B                                                                   0.0s
 => CACHED [ixnetwork  2/14] RUN set -ex &&     apt update &&     apt install -y     sudo     vim   0.0s
 => CACHED [ixnetwork  3/14] RUN rm -rf /var/lib/apt/lists/*                                        0.0s
 => CACHED [ixnetwork  4/14] RUN apt clean                                                          0.0s
 => CACHED [ixnetwork  5/14] RUN echo 'eval "$(pyenv init -)"' >> ~/.bashrc                         0.0s
 => CACHED [ixnetwork  6/14] RUN echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc              0.0s
 => CACHED [ixnetwork  7/14] RUN set -ex &&     curl https://pyenv.run | bash &&     pyenv install  0.0s
 => CACHED [ixnetwork  8/14] RUN set -ex &&     pip install     ansible     uv     pre-commit       0.0s
 => CACHED [ixnetwork  9/14] RUN set -ex &&     echo '    PubkeyAcceptedKeyTypes +ssh-rsa' | sudo   0.0s
 => CACHED [ixnetwork 10/14] ADD IxNetworkAPI26.0.2601.6PI.tar.gz /opt/                             0.0s
 => CACHED [ixnetwork 11/14] ADD IxNetworkAPI26.5.2644.8PI.tar.gz /opt/                             0.0s
 => CACHED [ixnetwork 12/14] RUN set -ex &&     uv venv /opt/ixia/venv/venv26.5 &&    . /opt/ixia/  0.0s
 => CACHED [ixnetwork 13/14] RUN set -ex &&     cd /home/ubuntu &&     cp .bashrc .bashrc_copy &&   0.0s
 => CACHED [ixnetwork 14/14] WORKDIR /IxNetwork                                                     0.0s
 => [ixnetwork26_5] exporting to image                                                              0.3s
 => => exporting layers                                                                             0.0s
 => => exporting manifest sha256:2c33f80a120c0835404b4202f5b7b0ba967878bc4225692a9a966af50bba353f   0.0s
 => => exporting config sha256:f01235d87b00a4233dbe921088a5d06e5a429ad3ae2d58e97efefe22564a785b     0.0s
 => => exporting attestation manifest sha256:1d759713e2a2ea4b610c4bbcef342db57d797aedfc3428f7cb543  0.1s
 => => exporting manifest list sha256:3b41fbbdda16534aac45e414d536007e5b950a4f6513c0eeb5a8f35729dd  0.1s
 => => naming to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                       0.0s
 => => unpacking to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                    0.1s
 => [ixnetwork] exporting to image                                                                  0.4s
 => => exporting layers                                                                             0.0s
 => => exporting manifest sha256:2e8ab1d87ad0898518c6dabf05bfa5d210b169460b88110742cca82dc7c3d427   0.0s
 => => exporting config sha256:53c52559451b713c636c1c53e9e4a9b9726f37cd6c219268b1ba03bf76027335     0.0s
 => => exporting attestation manifest sha256:7869cb95364e1986acc68fe97c734a7126f16837ad987730b0428  0.1s
 => => exporting manifest list sha256:4a7d4d65d0a9641619696e2ba516310b20cc3152d68275f349d2f36aed95  0.1s
 => => naming to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                       0.0s
 => => unpacking to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                    0.0s
 => [ixnetwork26_0] exporting to image                                                              0.4s
 => => exporting layers                                                                             0.0s
 => => exporting manifest sha256:0cfdf47e818f67d530afc409fb2e589e29dc2d57f898f1bf8b26f2bbecee4001   0.0s
 => => exporting config sha256:e8ab9350cd2e28366d77598be465fd9309f845d7943e0121e968772533d3abb2     0.1s
 => => exporting attestation manifest sha256:5d1c42fd7843f3b2973271db25e933c94023c45b72e17ec3fd426  0.1s
 => => exporting manifest list sha256:2bf87b61a5551aff9b598d42ee9efb45e611da818f1d4eb69e5f35c8159d  0.1s
 => => naming to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                       0.0s
 => => unpacking to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                    0.0s
 => [ixnetwork26_5] resolving provenance for metadata file                                          0.1s
 => [ixnetwork] resolving provenance for metadata file                                              0.1s
 => [ixnetwork26_0] resolving provenance for metadata file                                          0.0s
[+] build 1/1
 ✔ Image ghcr.io/daddy-knows-ixnetwork/ixnetwork:main Built                                          1.5s
seunyang@1H8618406V:~/support/daddy-knows-ixNetwork/ixnetwork-env$ 
```

## Run
```
seunyang@1H8618406V:~/support/daddy-knows-ixNetwork/ixnetwork-env$ docker compose run --remove-orphans ixnetwork
[+]  1/1te 1/1
 ✔ Container ixnetwork-env-ixnetwork26.0-run-96ec8ae1d518 Removed                                                                                                                                                      0.8s
Container ixnetwork-env-ixnetwork-run-54513aff48bb Creating 
Container ixnetwork-env-ixnetwork-run-54513aff48bb Created 
11:33:41 HL26.5 ubuntu@d93c40b32179 IxNetwork ±|main ✗|→ source /opt/ixia/venv/venv26.5/bin/activate
11:33:59 HL26.5 (venv26.5) ubuntu@d93c40b32179 IxNetwork ±|main ✗|→ 
11:35:48 HL26.5 (venv26.5) ubuntu@d93c40b32179 IxNetwork ±|main ✗|→ python
Python 3.14.7 (main, Aug 19 2026, 09:08:24) [GCC 13.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import ixnetwork_restpy
>>> exit
11:36:08 HL26.5 (venv26.5) ubuntu@d93c40b32179 IxNetwork ±|main ✗|→ 
```
