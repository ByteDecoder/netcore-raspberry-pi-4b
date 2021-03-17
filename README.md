# .Net Core && Raspberry  Pi IoT

.Net Core setup and publish

More in: https://docs.microsoft.com/en-us/dotnet/iot/deployment

```bash
curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin --runtime dotnet --version 3.1.13
curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin --runtime aspnetcore --version 3.1.13

curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin --runtime dotnet --version 5.0.4
curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin --runtime aspnetcore --version 5.0.4

echo 'export DOTNET_ROOT=$HOME/.dotnet' >> ~/.bashrc
echo 'export PATH=$PATH:$HOME/.dotnet' >> ~/.bashrc
source ~/.bashrc

scp -r /publish-location/* pi@raspberrypi:/home/pi/deployment-location/
```

## Troubleshooting with 5ghz networks

```bash
sudo iw wlan0 scan
sudo iw wlan0 scan | grep -A5 'freq: 5'

sudo nano /etc/default/crda set tu US
```
