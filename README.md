Список доменов, ограничивающих доступ из РФ в .json, .srs и .list (для Shadowrocket).

В Shadowrocket:
```yaml
Rule:
  Type: RULE-SET
  Policy: PROXY
  Rule Set: https://github.com/smolensky91/geosite-russia-outside/raw/main/geosite-russia-outside.list
```
В Nekobox:
```yaml
  {
    "route": {
        "auto_detect_interface": true,
        "rule_set": [
            {
                "download_detour": "proxy",
                "format": "binary",
                "tag": "geosite-russia-outside",
                "type": "remote",
                "update_interval": "1d",
                "url": "https://github.com/smolensky91/geosite-russia-outside/raw/main/geosite-russia-outside.srs"
            }
        ],
        "rules": [
            {
                "outbound": "proxy",
                "rule_set": [
                    "geosite-russia-outside"
                ]
            }
        ]
    }
}
```
