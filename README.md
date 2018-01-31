== ejs template engine SAMPLE
```javascript
import org.boon.Boon;
 
def jsonEditorOptions = Boon.fromJson(/{
        disable_edit_json: true,
        disable_properties: true,
        no_additional_properties: true,
        disable_collapse: true,
        disable_array_add: true,
        disable_array_delete: true,
        disable_array_reorder: true,
        theme: "bootstrap2",
        iconlib:"fontawesome4",
        schema: 
{
  "type": "object",
  "properties": {

    "project": {
       "propertyOrder" : 1,
       "format": "select",
       "type": "string",
       "enum": ["value1","value2"] 
      }
,
    "ctx": {
       "propertyOrder" : 2,
       "type": "string",
       "watch": { "pn": "project" },
       "template": "<%= pn %>"
      }

 
    }
 },
        startval: {
"project": "value1",
"ctx": "vale"
        }
}/);
```

and the result is an ENV var set like:

`VAR1={"ctx":"vale","project":"value1"}`
