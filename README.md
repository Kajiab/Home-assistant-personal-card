# HA-personal-card
Picture of personal card change by status

```yaml
type: custom:button-card
entity: person.thomas
name: Thomas

show_entity_picture: false
show_name: true

custom_fields:
  icon: |
    - platform: template
      sensors:
        value_template: "{{ states('person.thomas') }}"
      entity_picture_template: >
        {% if is_state('person.thomas', 'home') %}
          /local/Images/Thomas/home.jpeg
        {% elif is_state('person.thomas', 'away') %}
          /local/Images/Thomas/away.jpeg
        {% else %}
          /local/Images/Thomas/other.jpeg
        {% endif %}
styles:
  custom_fields:
    icon:
```

    Referrent https://community.home-assistant.io/t/person-card-change-image-according-to-status/726950/7
      - width: 80%
      - height: 80%
