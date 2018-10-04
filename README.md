# prsb-headings
Machine-readable downloads of the PRSB standard headings

```
xlsx/
    
json/
    crisis_care_summary.json
    e_discharge.json
    emergency_care_discharge.json
    mental_health_discharge.json
    outpatient_letters.json
```

### Method
These JSON files were created from the PRSB Standards by doing the following:

* search through the page source to find an element containing a `data-slug` id like `<div id="tree" data-slug="5a74e7557cd4311c55e391f1">`
* search the network tab for that hex string, which will show an XHR request like `admin-ajax.php?action=get_standard_tree&slug=5a74e7557cd4311c55e391f1`, containing all of the standard in a JSON format
* save to a JSON file
* prettify using `pretty-json` for the Atom editor
* remove superfluous occurrences of `&#xA0` (a non-breaking space character)

The data is fairly self-explanatory. These standards don't quite go into the detail of a 'schema' document, but they do define a higher-level general structure for a document and they specify the sorts of things that should be in the various documents. The field `"mro"` stands for 'Mandatory, Required or Optional status', which can cause some confusion because Mandatory and Required can seem to mean the same thing. For the sake of clarity, the PRSB definitions of these terms are:

```
mandatory  = MUST be included in the document, the document CANNOT be transmitted without this data
required   = IF this information is available to the sender it SHOULD be transmitted, but if it is not available to the sender then the document CAN still be transmitted
optional   = these fields are optional and can be populated as per the implementation requirements
```

If you have any feedback about the content of these standards please email the PRSB: [info@theprsb.org](info@theprsb.org)

If you have feedback regarding this transliteration of the standards into JSON then please create an Issue in this repo.

### Attribution/License
I figure that since these standards are publicly available on the web, via the PRSB tree browser, and as Excel documents, nobody will mind me publishing them in a machine readable format here. You never know, publishing them this way _might_ make it easier to implement the standards ;-)

Copyright 2018 The PRSB I Guess
CC-BY-SA Until I Hear Otherwise
[#publicmoneypubliccode](https://publiccode.eu/)
