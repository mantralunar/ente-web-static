# Ente Web Static

## Download latest release

```sh id="t6w88j"
curl -fL \
  https://github.com/mantralunar/ente-web-static/releases/latest/download/ente-web-static.tar.gz \
  -o ente-web-static.tar.gz
```

## Extract

```sh id="34d4tx"
mkdir -p ente-web-static
tar -xzf ente-web-static.tar.gz -C ente-web-static
cd ente-web-static
```

## Set Museum URL

```sh id="wwnn7o"
export ENTE_API_ORIGIN="https://museum.example.com"
```

## Replace placeholder

```sh id="ru7k9o"
find . -type f -name '*.js' -exec \
  sed -i.bak "s#ENTE_API_ORIGIN_PLACEHOLDER#$ENTE_API_ORIGIN#g" {} +
```

## Remove backup files

```sh id="5bsyea"
find . -type f -name '*.bak' -delete
```

## Verify

```sh id="m61yxh"
grep -R "ENTE_API_ORIGIN_PLACEHOLDER" .
```

No output means the replacement was successful.
