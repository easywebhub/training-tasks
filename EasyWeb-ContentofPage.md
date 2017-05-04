> Content file is defined with front-matter `json` format

```json
---json
{
    //default fields at order
    "slug" : "xxx",   
    "title" : "title of this page",
    "layout" : "",   
    "category" : "",  
    "tag" : [],   
    "date" : "create-of-time",    
    
    //page defined fields
    "__content__" : "main content for detail page"
}
---
```

### **Always show** fields
- `slug` : id of a pge, a part of url, auto generate from title e.g : abc => `http://domain.com/abc`, 
- `date`: 

### **Always hide** fields
- `layout`: the layout will be applied, could be changed to Show at Config Editor

### **Show/hide** fields
- category  
- tag 
- __content__
- other fields

### Config Editor
> fields showed on Form Editor based on the Config json file. 
- show properties on List Fields
```
    name:         key,
    displayName:  key,
    type:         'Text',
    displayType:  'ShortText',
    defaultValue: '',
    validations:  [],
    viewOnly:     false,
    required:     false
```





