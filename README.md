# YIPs

<!-- copyright 2020 yearn.finance && the contributors -->
<p align="center">
 <img src="https://rawcdn.githack.com/gist/sambacha/9a62174a080ead34271ff5d187a24343/raw/02cad2900f4cedb87895cc57729030e095d2869f/gh_banner.svg" align="right" width="350">
	<h1 align="left">YIPs</h1>
 <h3 align="center"> </h3>
 <p align="center">
<align="center">
 
![Validate](https://github.com/iearn-finance/YIPS/workflows/Validate/badge.svg) [![Discord](https://img.shields.io/discord/734804446353031319.svg?color=768AD4&label=discord&logo=https%3A%2F%2Fdiscordapp.com%2Fassets%2F8c9701b98ad4372b58f13fd9f65f966e.svg)](https://discordapp.com/channels/734804446353031319/) [![Telegram](https://img.shields.io/badge/chat-on%20Telegram-blue.svg)](https://t.me/yearnfinance) [![Twitter Follow](https://img.shields.io/twitter/follow/iearnfinance.svg?label=iearnfinance&style=social)](https://twitter.com/iearnfinance)

- [YIPs](#yips)
  * [Contributing](#contributing)
  * [YIP Statuses](#yip-statuses)
  * [Validation](#validation)
  

**Yearn Finance Improvement Proposals (YIPs)** describe standards for the Yearn platform, including:

- core protocol specification
- client APIs
- contract standards
- governance operations
- and more 
 
## Contributing

1.  Review [YIP-0](YIPS/yip-0.md).
2.  Fork the repository by clicking "Fork" in the top right.
3.  Add your YIP to your fork of the repository. There is a [template YIP here](yip-X.md).
4.  Submit a Pull Request to Yearn's [YIPs repository](https://github.com/iearn-finance/YIPS/).

Your first PR should be a first draft of the final YIP. It must meet the formatting criteria enforced by the build (largely, correct metadata in the header). An editor will manually review the first PR for a new YIP and assign it a number before merging it. Make sure you include a `discussions-to` header with the URL to a new thread on [gov.yearn.finance](https://gov.yearn.finance/) where people can discuss the YIP as a whole.

If your YIP requires images, the image files should be included in a subdirectory of the `assets` folder for that YIP as follow: `assets/yip-X` (for yip **X**). When linking to an image in the YIP, use relative links such as `../assets/yip-X/image.png`.

When you believe your YIP is mature and ready to progress past the WIP phase, you should ask to have your issue added to the next governance call where it can be discussed for inclusion in a future platform upgrade. If the community agrees to include it, the YIP editors will update the state of your YIP to 'Approved'.

## YIP Statuses

- **WIP** - a YIP that is still being developed.
- **Proposed** - a YIP that is ready to be reviewed in a governance call.
- **Approved** - a YIP that has been accepted for implementation by the Yearn community.
- **Implemented** - a YIP that has been released to mainnet.
- **Rejected** - a YIP that has been rejected.
- **Withdrawn** - a YIP that has been withdrawn by the author(s).
- **Deferred** - a YIP that is pending another YIP/some other change that should be bundled with it together.
- **Moribund** - a YIP that was implemented but is now obsolete and requires no explicit replacement.

## Validation

YIPs must pass some validation tests. The YIP repository ensures this by running tests using [html-proofer](https://rubygems.org/gems/html-proofer) and [yip_validator](https://rubygems.org/gems/yip_validator).

It is possible to run the YIP validator locally:

```
gem install yip_validator
yip_validator <INPUT_FILES>
```

## YIP Geneartor

A YIP Generator is available [as a nodejs package here](https://github.com/sambacha/generator-yyip).

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
