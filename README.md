EU VAT Rates as JSON
====================

This static JSON file provides a simple to consume JSON document, containing a list of VAT rates per country in the European Union.

## How it works

Considering these VAT rates rarely change, **cache the data on your system**, so [clone the repository](https://github.com/benbucksch/eu-vat-rates) or install it into your project with [npm](https://www.npmjs.com/package/eu-vat-rates) or yarn: `npm install euvatrates.com`

Simply load `rates.json` as JSON. The data structure is pretty self explanatory JSON. There's a `last_updated` ISO 8601 timestamp in the root that tells you when the last VAT change (or bug fix) was made, and there is a disclaimer. The `rates` object contains all the different rates per country, based on its 2 character country code.

The rate object contains the country name, the local name of the tax in the local language, its abbreviation, and a couple of different tax rates that exist in the country. The values are always numeric (with decimals), or a boolean `false` if the rate is not used in the country.

The currently returned rate types are `standard_rate`, `reduced_rate`, `reduced_rate_alt`, `super_reduced_rate` and `parking_rate`. Which VAT rate you need to use, depends on the type of product or service you are providing and to whom you are providing it. It is best to consult someone knowledgeable on that, like your accountant. [This official EU Document also contains a table indicating what rates to apply.](http://ec.europa.eu/taxation_customs/resources/documents/taxation/vat/how_vat_works/rates/vat_rates_en.pdf) Exceptions or exemptions may apply per country.

## Contributing

Simply send a pull request! For changes to `rates.json` include the source for the change in the commit message, and also add it to the Data Sources list in `index.html` if it's a new resource.

## License and Disclaimer

This project is licensed under the MIT License.

This data is compiled from official European Commission and other sources to be as accurate as possible, however no guarantee of accuracy nor timely updates is provided. Use at your own risk.
