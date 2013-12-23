ABAP2yUML
================================


Have you ever skipped the documentation stage of a project due to "lack of time"? Do you use ABAP Objects to write your SAP Applications? If so, we can help you generate some cool documentation automatically.


ABAP2yUML is an UML generator based on yUML. Isn't there a SAP standard tool for this? Yes there is but here are the advantages only ABAP2yUML offer to you:

* No need for recent SAP Logon
* No need for recent SAP NetWeaver
* No need for a specific Java version
* No need to configure system settings
* Customizable
* Open Source (you can contribute)
* Integrated with yUML
* 100% Objected Oriented
* Fast
* And last, ridiculously simple to be used. 


### Example

Supposing you need to generate a simple UML class diagram for the class the very famous class CL_SALV_TABLE. All you need to do is:

```ABAP﻿

DATA o_wb_any_class TYPE﻿REF TO zcl_wb_class. " ABAP WB Objects Framework
wa_seoclskey-clsname = 'CL_SALV_TABLE'.

CREATE OBJECT o_wb_any_class
	EXPORTING
		﻿﻿im_clskey = wa_seoclskey.

o_wb_any_class->zif_wb_object~load( ).

DATA o_yuml_any_class TYPE REF TO zcl_yuml_class.

CREATE OBJECT o_yuml_any_class
	EXPORTING
		﻿﻿﻿im_wb_class = o_wb_any_class.

DATA v_yuml_code TYPE string.

v_yuml_code = o_yuml_any_class->zif_yuml_concept~generate_code( ).

WRITE: v_yuml_code.
```

... and it's done! Now you get the output (variable v_yuml_code) and visit http://yuml.me.
Draw a class diagram pasting the output and you will get the following result:

http://yuml.me/e234e605


## System Requirements

This projects is developed using SAP NetWeaver Trial Edition (SAP NetWeaver 7.31 Support Package 4). We do our best to keep a modern project so at the moment there is no guarantee it works perfectly on previous releases. We would love your support to test it if you have older releases and tell us possible issues.

You should have installed ABAP WB Objects Framework as ABAP2yUML uses it. But you don't need to worry as everything is well documented.

## Installation

The installation of this projects comes as SAPLink files so you should have it installed into your system. Refer to the Installation page for more details.

## Documentation

Most open source projects are not documented. This has no intentions to be another example. Refer to the Wiki if you are looking for documentation.

## Contributors

[Fábio Pagoti](http://br.linkedin.com/in/fabiopagoti/) - Product Architect

## Want to contribute? 

There are many ways to contribute. Don't worry if you are not (yet) an ABAP developer. Here are some ways you can help support this project:

* Coding
* Testing (UX, Security, Performance, Design)
* Using
* Reviewing documentation
* Reporting bugs
* Suggesting enhancements
* Sharing among friends, SCN, Facebook, Twitter, LinkedIn, etc

## Special thanks to:

* Who collaborate on this project sharing it on SAP Community Network, Facebook, Twitter, LinkedIn

[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/fabiopagoti/wb-objects/trend.png)](https://bitdeli.com/free "Bitdeli Badge")