# Last-Called-Alexa

For the full video, go here: https://youtu.be/cLv0CGgoTJ0


| Last Called Alexa Yaml - Before 0.115 |
| --- |

```yaml
- platform: template
  sensors:
    last_alexa:
      entity_id:
        - media_player.desk_dot
        - media_player.bedroom_dot
        - media_player.this_device
      value_template: >
        {{ states.media_player | selectattr('attributes.last_called','eq',True) | map(attribute='entity_id') | first }}
```

| Last Called Alexa Yaml - After 0.115 |
| --- |

:warning: **entity_id:** is no longer supported. You can simply omit those lines

```yaml
- platform: template
  sensors:
    last_alexa:
      value_template: >
        {{ states.media_player | selectattr('attributes.last_called','eq',True) | map(attribute='entity_id') | first }}
```
---
### 🤝 Found this useful, want to say 'Thanks' and support my efforts. CHEERS🍺
| Buy me a Coffee | PATREON |
|-----------------|---------|
| [![Buy Me A Coffee](https://img.shields.io/badge/Buy%20Me%20A%20Coffee-donate-yellow.svg?style=flat-square&logo=buy-me-a-coffee)](https://www.buymeacoffee.com/3ative) | [![Patreon](https://img.shields.io/badge/Patreon-support-red.svg?style=flat-square&logo=patreon)](https://www.patreon.com/3ative) |
---
