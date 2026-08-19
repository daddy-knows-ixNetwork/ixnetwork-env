# ixnetwork-env
ixnetwork script development environment for HLTAPI and IxNetwork RestPy

# how to build and run

## Build
```
seunyang@1H8618406V:~/support/daddy-knows-ixNetwork/ixnetwork-env$ docker compose build
[+] Building 19.5s (25/25) FINISHED                                                                                                                                                                                        
 => [internal] load local bake definitions                                                                                                                                                                            0.0s
 => => reading from stdin 1.84kB                                                                                                                                                                                      0.0s
 => [ixnetwork internal] load build definition from Dockerfile                                                                                                                                                        0.0s
 => => transferring dockerfile: 5.62kB                                                                                                                                                                                0.0s
 => [ixnetwork internal] load metadata for docker.io/library/ubuntu:24.04                                                                                                                                             0.5s
 => [ixnetwork internal] load .dockerignore                                                                                                                                                                           0.0s
 => => transferring context: 2B                                                                                                                                                                                       0.0s
 => [ixnetwork26_0  1/14] FROM docker.io/library/ubuntu:24.04@sha256:d78ab76437b1afc5f01e223d6bf0172763f404bb166441328845adbef44518cb                                                                                 0.0s
 => => resolve docker.io/library/ubuntu:24.04@sha256:d78ab76437b1afc5f01e223d6bf0172763f404bb166441328845adbef44518cb                                                                                                 0.0s
 => [ixnetwork26_0 internal] load build context                                                                                                                                                                       0.0s
 => => transferring context: 110B                                                                                                                                                                                     0.0s
 => CACHED [ixnetwork26_0  2/14] RUN set -ex &&     apt update &&     apt install -y     sudo     vim     git     curl     build-essential     libbz2-dev     libffi-dev     liblzma-dev     libncursesw5-dev     li  0.0s
 => CACHED [ixnetwork26_0  3/14] RUN rm -rf /var/lib/apt/lists/*                                                                                                                                                      0.0s
 => CACHED [ixnetwork26_0  4/14] RUN apt clean                                                                                                                                                                        0.0s
 => CACHED [ixnetwork26_0  5/14] RUN echo 'eval "$(pyenv init -)"' >> ~/.bashrc                                                                                                                                       0.0s
 => CACHED [ixnetwork26_0  6/14] RUN echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bashrc                                                                                                                            0.0s
 => CACHED [ixnetwork26_0  7/14] RUN set -ex &&     curl https://pyenv.run | bash &&     pyenv install 3.14 &&     pyenv global 3.14 &&     pip install --upgrade pip                                                 0.0s
 => CACHED [ixnetwork26_0  8/14] RUN set -ex &&     pip install     ansible     uv     pre-commit     jupyterlab                                                                                                      0.0s
 => CACHED [ixnetwork26_0  9/14] RUN set -ex &&     echo '    PubkeyAcceptedKeyTypes +ssh-rsa' | sudo tee -a /etc/ssh/ssh_config &&     echo '    HostKeyAlgorithms +ssh-rsa' | sudo tee -a /etc/ssh/ssh_config       0.0s
 => CACHED [ixnetwork26_0 10/14] ADD IxNetworkAPI26.0.2601.6PI.tar.gz /opt/                                                                                                                                           0.0s
 => CACHED [ixnetwork26_0 11/14] ADD IxNetworkAPI26.5.2644.8PI.tar.gz /opt/                                                                                                                                           0.0s
 => [ixnetwork26_5 12/14] RUN set -ex &&     uv venv /opt/ixia/venv/venv26.5 &&    . /opt/ixia/venv/venv26.5/bin/activate &&    uv pip install -r /opt/ixia/ixnetwork/26.5.2644.8/lib/PythonApi/requirements.txt &&   5.2s
 => [ixnetwork26_0 13/14] RUN set -ex &&     cd /home/ubuntu &&     cp .bashrc .bashrc_copy &&     bash -c "$(curl -fsSL https://raw.githubusercontent.com/ohmybash/oh-my-bash/master/tools/install.sh)" &&     cat   1.5s
 => [ixnetwork26_0 14/14] WORKDIR /IxNetwork                                                                                                                                                                          0.1s
 => [ixnetwork26_5] exporting to image                                                                                                                                                                               11.9s
 => => exporting layers                                                                                                                                                                                               5.9s
 => => exporting manifest sha256:cc979f31ce7f651e241f6a9498a0e75ccc0735af34ad5f823ff59fa36d71d7bd                                                                                                                     0.0s
 => => exporting config sha256:b0f297475174aa588129fd8594d2839f131b751b7597846e1a1091f553ede851                                                                                                                       0.0s
 => => exporting attestation manifest sha256:d896e729eba5389d51c7bce07c8729f769af45145e7401bac06e71f021319d9c                                                                                                         0.0s
 => => exporting manifest list sha256:c8e6bb507576097570b09875e1eb25e6af44af59643637571284cb4328227771                                                                                                                0.0s
 => => naming to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                                                                                                                                         0.0s
 => => unpacking to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                                                                                                                                      5.8s
 => [ixnetwork26_0] exporting to image                                                                                                                                                                               11.9s
 => => exporting layers                                                                                                                                                                                               5.9s
 => => exporting manifest sha256:15beb94494ea21a3f6534b69f437cc5f2f6458756e4fa6c69cbf9e438793ec47                                                                                                                     0.0s
 => => exporting config sha256:6029e720340180f1080ef88de139d50005fbbbfe323fb41395a5d17cd438c16a                                                                                                                       0.0s
 => => exporting attestation manifest sha256:86d9cfebc9c3b7665e9c40fa86fd0e2e447ab08f5a2506910b6b180c323ff219                                                                                                         0.0s
 => => exporting manifest list sha256:d5973fec33c1c4725af8c660f0b812c5dc64c468d8d87395436e1efa93c7f149                                                                                                                0.0s
 => => naming to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                                                                                                                                         0.0s
 => => unpacking to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                                                                                                                                      5.8s
 => [ixnetwork] exporting to image                                                                                                                                                                                   11.9s
 => => exporting layers                                                                                                                                                                                               5.9s
 => => exporting manifest sha256:9812d0e7f47989bb6192ef5f9bac0d7694bea307069e6fcd3447a5723e5e5e20                                                                                                                     0.0s
 => => exporting config sha256:ef943d2e109cafdde32be3b021c7460b2bc718f9379cc3de1888bcddfc468a71                                                                                                                       0.0s
 => => exporting attestation manifest sha256:d19d442146d3737155685042dbc63bb7ce945c9d679c15e58fb3cdfebc6d1325                                                                                                         0.0s
 => => exporting manifest list sha256:cef9a15e98b9210a0a38b7a37ff2723990086bb330d48a89e9401f7c55ba830f                                                                                                                0.0s
 => => naming to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                                                                                                                                         0.0s
 => => unpacking to ghcr.io/daddy-knows-ixnetwork/ixnetwork:main                                                                                                                                                      5.8s
 => [ixnetwork26_0] resolving provenance for metadata file                                                                                                                                                            0.0s
 => [ixnetwork] resolving provenance for metadata file                                                                                                                                                                0.0s
 => [ixnetwork26_5] resolving provenance for metadata file                                                                                                                                                            0.0s
[+] build 1/1
 ✔ Image ghcr.io/daddy-knows-ixnetwork/ixnetwork:main Built                                                                                                                                                           19.5s
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