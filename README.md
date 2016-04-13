# EmailPush
Free tool to send HTML email to intended recipients in bulk. 


### Configuration

**Defining Input File Layout**

Layout is a configuration file which is used to identify the file and its properties. This configuration file provides information like 
  - What kind of input file we deal with?
  - Does it has header record? 
  - What are the delimiter(record as well as field)?
  - How many fields we deal with? 
  - In which order they structured in the file? 
  - What type of data does the filed holds?
  - Is there any storage limit expected? 
  - Is there any input format defined? (Applicable to date datatype)

and many more. 


```javascript
/* JSON to define input file layout skeleton*/
{
	"layout-id": "",
	"layout-description": "",
	"layout-records-delimiter": "",
	"layout-records-header-row-flag": "",
	"layout-field-delimiter": "",
	"source-fields": [
		{
			"field-id": "",
			"field-description": "",
			"field-order": "",
			"field-datatype": "",
			"field-size": "",
			"field-format": ""
		}
	]
}
```

```javascript
/* Example:: Input file layout for a customer information received in csv format. */
{
    "layout-id": "customer_info_layout",
    "layout-description": "File holds customer information",
    "layout-records-delimiter": "\n",
    "layout-records-header-row-flag": true,
    "layout-field-delimiter": ",",
    "source-fields": [
        {
            "field-id": "customer_id",
            "field-description": "Customer ID",
            "field-order": "1",
            "field-datatype": "Integer",
            "field-size": "10"
        },
		{
            "field-id": "customer_name",
            "field-description": "Customer Complete Name",
            "field-order": "2",
            "field-datatype": "String",
            "field-size": "50"
        },
		{
            "field-id": "customer_email",
            "field-description": "Customer Email Address",
            "field-order": "3",
            "field-datatype": "String",
            "field-size": "50"
        },
		{
            "field-id": "customer_dob",
            "field-description": "Customer Date of Birth",
            "field-order": "4",
            "field-datatype": "Date",
            "field-format": "DD/MM/YYYY"
        },
		{
            "field-id": "customer_active",
            "field-description": "Customer active flag",
            "field-order": "5",
            "field-datatype": "Boolean"
        }
    ]
}
```
