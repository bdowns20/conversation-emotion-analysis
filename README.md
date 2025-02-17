# model-alignment


## Setup 


### Connecting to AI Platform

- **Visit [AI Platform Page for details](https://ai-platform.pages.mitre.org/resources/compute/)**
  - Register a new token/password for teleport here: https://register.aip.mitre.org/complete
  - Log in to teleport using that token/password: https://teleport.aip.mitre.org/web/cluster/teleport.aip.mitre.org/resources
  - Make sure you have access to `aip-nipr-gpt` VM: https://register.aip.mitre.org/nodes
    - test with `tsh login --proxy=teleport.aip.mitre.org` then `tsh ls`
  - SSH and VSCode setup: https://goteleport.com/docs/enroll-resources/server-access/guides/vscode/
    - `tsh config --proxy teleport.aip.mitre.org` Append the resulting configuration snippet into your SSH config file
    - Make sure to add your `User` under the teleport host in your config file
  - Once you have access, connect using: `tsh ssh aip-nipr-gpt`
    - If you do not have tsh set up, follow instructions here: https://ai-platform.pages.mitre.org/resources/compute/
    - For Windows users, you may need to use the --user flag for tsh, then access the VM using: `tsh ssh [USERNAME]@aip-nipr-gpt`

### General Setup

```
python3 -m virtualenv <env-name>
source <env-name>/bin/activate
pip install -e .


# Update SSL certs courtesy of mitre-pki: https://gitlab.mitre.org/mitre-scripts/mitre-pki#maclinux
curl -ksSL https://gitlab.mitre.org/mitre-scripts/mitre-pki/raw/master/tool_scripts/install_certs.sh | MODE=python sh

```