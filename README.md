![plentymarkets Logo](http://www.plentymarkets.eu/layout/pm/images/logo/plentymarkets-logo.jpg)

# plenty-external-tool

This is a plugin example for an external tool to show on marketplace.

## plugin.json

|      |     |     |
|------|-----|-----|
| type  | An external tool must be of type tool. (required) |
| isExternalTool | The value of this field must be of type bool. (required) |
| directDownloadLinks | An array of strings that provides direct download links for different operating systems, e.g.  "directDownloadLinks" : {"Windows":"download-link", "MacOs":"download-link", "Linux":"download-link"} |
| forwardLink | A string that provides a forward link to a website where the customer can download the tool, e.g.  "forwardLink" : "https://download-page.com" |

Note: Any external tool requires at least 'directDownloadLinks' or 'forwardLink' to be filled.



