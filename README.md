# Practice - VOICEVOX ENGINE

## Run

```shell
docker-compose up -d

mkdir -p build

curl -s \
    -X POST \
    "127.0.0.1:50021/audio_query?speaker=1"\
    --get --data-urlencode text@text.txt \
    > build/query.json

curl -s \
    -H "Content-Type: application/json" \
    -X POST \
    -d @build/query.json \
    "127.0.0.1:50021/synthesis?speaker=1" \
    > build/audio.wav
```

## Reference

- [VOICEVOX/voicevox_engine > Docker イメージ](https://github.com/VOICEVOX/voicevox_engine#docker-イメージ)
