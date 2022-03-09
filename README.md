# What is lkmlstyle?

**lkmlstyle is a flexible, command-line style checker for LookML.** lkmlstyle checks LookML to see if it follows predefined **rules**, returning lines in your code that don't follow the rules.

## Installation

Install lkmlstyle with pip:

```
pip install lkmlstyle
```

If the installation was successful, you should be able to run this command to see a table of available style rules.

```
lkmlstyle rules
```

## Getting Started

First, clone the Git repo for your Looker project to your local environment so lkmlstyle can find `.lkml` files in your environment.

### Specifying files to check

Next, run lkmlstyle with the path to your local Looker project repo. lkmlstyle will check all files in your project that end in `.lkml` and display any rule violations.

```
lkmlstyle repos/product-analytics
```

You can pass individual or multiple files to lkmlstyle to valiate them specifically.

```
lkmlstyle repos/product-analytics/views/sessions.view.lkml
```

## Customizing the ruleset

### Ignoring rules

If you see rules you'd like to ignore, you can add the `--ignore` option and the codes for the offending rules to exclude them from testing.

```
lkmlstyle repos/product-analytics/views/sessions.view.lkml --ignore D106 D107 M101
```

### Isolating rules

Similarly, if you'd like to focus on a few rules at a time, you can provide rule codes to `--select` to _only_ test those rules.

```
lkmlstyle repos/product-analytics/views/sessions.view.lkml --select D101
```

### Seeing the rationale for rules

If you're confused by a rule or curious why a Looker developer might want to follow it, you can add the `--show-rationale` option. lkmlstyle will display some information about why the rule exists.

```
lkmlstyle sessions.view.lkml orders.view.lkml --show-rationale
```

### Showing all rules

To display all the rules and rationales defined in lkmlstyle, run this command.

```
lkmlstyle rules
```

_lkmlstyle is maintained by the team at [Spectacles](https://spectacles.dev)—a continuous integration tool for Looker and LookML._
