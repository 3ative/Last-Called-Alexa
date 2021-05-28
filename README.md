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


🎁 Found this useful or want to say 'thanks' and support my efforts...

[![BMC](https://www.buymeacoffee.com/assets/img/custom_images/white_img.png)](https://www.buymeacoffee.com/3ative) **And leave a me a message to let me know.**  ❤

🍺 CHEERS! 👍

