# Glances

```console
% sudo apt install -y glances
% sudo systemctl enable glances.service
% sudo systemctl stop glances.service
% sudo export GLANCES_VERSION=$(glances -V | head -n 1 | awk '{print $2}' | sed 's/^v//')
% wget "https://github.com/nicolargo/glances/archive/refs/tags/v${GLANCES_VERSION}.tar.gz"
% tar -xzf v${GLANCES_VERSION}.tar.gz
% sudo cp -r glances-${GLANCES_VERSION}/glances/outputs/static/public/ /usr/lib/python3/dist-packages/glances/outputs/static/
% sudo sed -i '/ExecStart=\/usr\/bin\/glances -s -B 127.0.0.1/c\ExecStart=\/usr\/bin\/glances -w -B 0.0.0.0 -t 10 -p 61208' /usr/lib/systemd/system/glances.service
% sudo systemctl daemon-reload
% sudo systemctl start glances.service
```


