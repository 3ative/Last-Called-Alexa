# Last-Called-Alexa

For the full video, go here: https://youtu.be/cLv0CGgoTJ0

Last Called Alexa Yaml
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


<a href="https://www.buymeacoffee.com/3ative" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-blue.png" alt="Buy Me A Coffee" style="height: 51px !important;width: 217px !important;" ></a>
