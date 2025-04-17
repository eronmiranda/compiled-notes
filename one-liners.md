# Homelab One-liner Commands

## Print all Docker containers IP address from a compose file

```sh
for s in `docker compose ps -q`; do echo ip of `docker inspect -f "{{.Name}}" $s` is `docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' $s`; done
```

## Get Docker Container IP Address

```sh
docker inspect service_name | jq '.[].NetworkSettings.Networks.network_name.IPAddress'
```

## Enable/Disable Ubuntu GUI on Boot

To Disable GUI:

```sh
sudo systemctl set-default multi-user.target
```

To Enable GUI:

```sh
sudo systemctl set-default graphical.target
```

## Start GUI manually from a command line

```sh
sudo systemctl start gdm3
OR
sudo systemctl start lightdm
```

## Print Public IP

```sh
dig +short myip.opendns.com @resolver1.opendns.com
```

## Create Directories Structure

```sh
# Replace with actual categories and service names
sudo mkdir -p /media/{media_type1,media_type2,downloads/type} /configs/{app1,app2,app3,app4,app5,app6,app7,app8}

```

## Check Batter Information

In Ubuntu:

``` sh
upower -i /org/freedesktop/UPower/devices/battery_BAT0 | grep -E "state|to\ full|percentage"
```

## Update Packages

```sh
sudo apt-get -q update && sudo apt-get -q upgrade
```

## Remove Old Versions of Docker

```sh
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

## Convert All .js file into a .jsx

```sh
for f in *.js; do git mv "$f" "${f%.js}.jsx"; done
```
