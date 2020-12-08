# FAQ Server build on top of Rasa AI

These instructions are not finished. Will be finished tomorrow :)

## Install instructions

```shell
python3.6m -m venv ./venv
source ./venv/bin/activate
pip3 install -U pip
pip3 install rasa

# Optional, if you get some errors you can try this
pip3 --use-feature=2020-resolver install rasa

git clone https://github.com/LiveHelperChat/faq-rasa.git && cd faq-rasa

rasa train

# Run as API server
rasa run
```

To test
```shell
curl --request POST   --url http://localhost:5005/webhooks/rest/webhook   --header 'content-type: application/json'   --data '{
  "message": "weather berlin"
}'
```

Expected output

```json
[{"recipient_id":"default","text":"Oh, it does look sunny right now in Berlin."}]
```
