---
yip: <to be assigned>
title: improve-yip-categories
status: WIP 
author: sam bacha, @sambacha <sam@freighttrust.com>
discussions-to: https://gov.yearn.finance/t/proposal-add-new-statuses-to-yip-proposals-non-protocol-change/3608

created: 2020-08-24
requires (*optional): <YIP number(s)>
implementation (*optional): <Added if YIP passes>
---



## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->

Add new `status`(s) to `YIPs` so that author(s) may better manage their `YIPs` in the context of community collaboration and so that governance is given the proper procedures to foster community cooperation.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the YIP is implemented, not *why* it should be done or *how* it will be done. If the YIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->


This will *only* add to the current state of `proposal YIPs` in that it only changes the `status` of a `YIP`. It does not add any `protocol` changes: only documentation and governance procedures (off chain only).

I proposal the following changes to reflect a new state of possible 'YIPs':

1. Modifying YIP Templates
2. Modifying YIP Validator Gemfile
3. Modifying YIP README file


## Motivation
<!--This is the problem statement. This is the *why* of the YIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the YIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the YIP will address the issue!-->
> The current state of procedures for `YIPS` is inadequate as it unnecessarily limits the possible outcomes of a proposed `YIP` while not affording both the author(s) nor the governance council flexibility in being able to deal with community driven `YIPs`

This is a *documentation* and *procedure* change. In fact there is no explicit description for proposing such changes in governance *(that I could find).*

This change is needed as it better explains the *intent* of the YIP format to author(s). It also provides for governance additional functionality in their procedures so as to not potentially 'alienate' author(s) by rejecting a YIP when it could have been withdrawn. This ensures that also the author(s) are active in the process of their submitted proposal and in the larger community (in so far as they are knowledgable about other potentially competing YIPS.)

## Specification

*Additions in 'BOLD'*

Proposed - a YIP that is ready to be reviewed in a governance call.
Approved - a YIP that has been accepted for implementation by the yEarn community.
Implemented - a YIP that has been released to mainnet.
Rejected - a YIP that has been rejected.
**Withdrawn - a YIP that has been withdrawn by the author(s).**
**Deferred - a YIP that governance has decided to wait for another YIP/some other change that should be bundled with it together**
**Moribund - a YIP that was once Implemeneted. It is now Obsolete 'AND' requires no explicit replacement.**

The "Withdrawn" status is similar - it means that the YIP author has decided that the YIP is actually a 'bad' idea, or has accepted that a competing proposal is a better alternative.


### Workflow Specification
```
Proposed -> Approved -> Implemented
  ^                     |
  +----> Rejected       +----> Moribund
  |
  +----> Withdrawn
  v
Deferred
```


#### New Statuses for YIPs 

> To be added are the following

[Withdrawn](/EfryOm69Sf-iM4TCasQuJA)
[Moribund](/igo8dKVnRjq8Xxyql9GOxQ)
[Deferred](/MPwJ8Sa2Se-7qFBlEvDEBw)


### Overview
<!--This is a high level overview of *how* the YIP will solve the problem. The overview should clearly describe how the new feature will be implemented.-->

#### New YIP statuses
- Withdrawn
Means that the YIP author has decided that the YIP is actually a bad idea, or has accepted that a competing proposal is a better alternative.
- Moribund
Obsolete and requires no explicit replacement, it SHOULD be marked "Moribund"
- Deferred
Governance placed status upon a YIP that means that they would like to know more information, or that they would like to see if the author(s) can work with another proposed YIP and combine it into a single YIP, etc.


### Rationale

The reasoning behind this is that it is unclear what will happen to a YIP should material facts change during its inital formal proposal and when its actually voted on by governance. Changes may be introduced between then, and the author may want to withdraw the proposal. This also frees up the governance concuil in that they are no longer obligated to reject every single YIP that may no longer be relevent, instead sharing the responsibility with the actual author(s). 

### Technical Specification
<!--
NOTE: NO PROTOCOL CHANGES ARE PROPOSED 
THE ONLY TECHNICAL CHANGES ARE IN THE RUBY VALIDATION PROCESS FOR YIPS
-->
Technical implementation involves:

* changes in the validation Gemfile 
* changes in the template `.md` file

#### Changes in Template `.md` file

Below is a sample `.yaml` file to illustrate the _new_ header that should be used in the `yip-template.md` file

```yaml
---
YIP: <YIP number>
Title: <YIP title>
Author: < firstName, lastName, @githubUsrName, contact@address.com >
Type: <Informational | Standards Track>
Status: <WIP | Proposed | Approved | Deferred | Withdrawn | Rejected |
           Implemented | Replaced | Moribund>
    Version: <major>[.<minor>]
    Created: <date created on, in ISO 8601 (yyyy-mm-dd) format>
    Requires (*optional): <YIP number(s)>
    Implementation (*optional): <Added if YIP passes>

Discussions-to: <Create a new thread on https://gov.yearn.finance/ and drop the link here>

* Requires: <YIP numbers>
* Replaces: <YIP numbers>
* Replaced-By: <YIP number>
---
```

#### YIP Validator (Ruby Gem)

> current version: `1.0.2`, should be bumpbed to `1.1.0`
Changes located [github.com/iearn-finance/yip_validator/blob/master/lib/yip_validator/validator.rb#L25](https://github.com/iearn-finance/yip_validator/blob/master/lib/yip_validator/validator.rb#L25)

```ruby
    validates_inclusion_of :status, in: ['WIP', 'Proposed', 'Approved', 'Implemented', 'Rejected']
```
```ruby
    validates_inclusion_of :status, in: ['WIP', 'Proposed', 'Approved', 'Implemented', 'Rejected', 'Withdrawn', 'Deferred', 'Moribund']
```

See Files Changed here [https://github.com/sambacha/yip_validator/tree/YIP-Proposed](https://github.com/sambacha/yip_validator/tree/YIP-Proposed)

### Test Cases

See `travis-ci` logs for the `Rub Gem` update here [https://travis-ci.com/github/sambacha/yip_validator/builds/181226022](https://travis-ci.com/github/sambacha/yip_validator/builds/181226022)

```bash
total:2, valid:2, invalid:0, errors:0
	statuses: [["Withdrawn", 1], ["Implemented", 1]]
  raises exception if it includes invalid yips
spec/fixtures/invalid/yip-7.md is NOT valid:	 {:status=>["is not included in the list"]}

```

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
