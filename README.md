
# Development, on a Mac

## Initial Setup

    bash dev/init.sh

## Running

    bash dev/run.sh
    …
    bash dev/stop.sh


# Production, on CoreOS

## Initial Setup
```bash
for x in db app web; do
  docker build -t $x $x
  sudo systemctl enable $PWD/$x/$x.service
  sudo systemctl start $x.service
done
```

## Rebuilding
e.g. for `app`:

    docker build -t app app
    sudo systemctl restart app.service
