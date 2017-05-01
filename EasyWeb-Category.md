A single category node contains
```json
{
    "children": [],
    "parent": null,
    "href": 'url',
    "files": [],
    "category": 'cacbenh.mat',	
    "sortBy": "date",
    "reverse": false,
    "metadata": 
    {
	 "ten": "Các bệnh mat "
    },
    "displayName": "các bệnh.mắt",
    "perPage": 10,
    "noPageOne": true,
    "layout": "forum-chuyentrang.category.html",
    "first": ":categoryPath/index.htm",
    "path": ":categoryPath/page/:num/index.html"
}
```
Access using {{#with}} syntax
```
{{#with (lookupCategory AllCategory 'path-of-category') }}
   {{href}}
   {{metadata.ten}}
   {{children.[0]}}  // or {{children.0}}
{{/with}}
```

Access allItems of Category
```
{{#with AllCategory.files}}

{{/with}}
```
### A child category node is have structure as same as above
# Pagination
to access data of current category use **pagination** variable
### pagination structure
```
	 {
		template: pageOptions.template,
		layout: pageOptions.layout,
		contents: pageOptions.pageContents,
		href: interpolate(pageOptions.path, pagination),
		metadata: pageOptions.metadata ? pageOptions.metadata : {},
		pagination: {
			name: name,
			category: category,
			displayName: pageOptions.displayName,
			categoryPath: categoryPath,
			index: length,
			num: length + 1,
			pages: pages,
			files: [],
			getPages: createPagesUtility(pages, length),
			previous: ,
			next: ,
			first: ,
			last: ,
		}
		AllCategory: metadata.AllCategory,		
	}
```

# helpers
```
/**
    lookupCategory
    @param {object} [AllCategory] - category tree object
    @param {string} [categoryPath] - category full path
    @param {string} [propertyPath] - string object path like in lookupEx
    @returns {object} - a category object
*/
lookupCategory AllCategory 'tin-tuc.thoi-su.quoc-te' 'children'
```

#### genBreadcrumb AllCategory 'tin-tuc.thoi-su.quoc-te'
return array of category object

#### lookupEx Object 'aa.bb.cc'
return value of Object.aa.bb.cc

### handlebar array access:
	.:number
	.[:number]

		
