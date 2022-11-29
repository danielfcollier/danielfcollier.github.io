---
title: "JSON and YAML Cheat Sheet"
date: 2022-10-22T08:09:47-03:00
Description: ""
Summary: "Simple CLI commands to format and access properties when doing request with cURL"
Tags: [json, yaml, cli]
Categories: [linux]
DisableComments: false
---

# Shell Terminal

## Access JSON properties
```bash
| jq .
| jq ".prop1,prop2.index,.[0]"
| jq ".[] | .location"
| jq ".[] | select(.location == "Stockholm")"
| jq "to_entries[]"
```

## Convert yaml to json
```bash
yq -o=json . <yaml-file> > <json-file>
```

## Convert json to yaml
```bash
yq -o=json . <yaml-file>
```

# JavaScript

## Pretty print in JS
```javascript
console.log(JSON.stringify(json, null, 4))
```