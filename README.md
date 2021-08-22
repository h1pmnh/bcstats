## Description

`bcstats` is a tool which allows Bugcrowd researchers to download information about all accessible programs (public and private) into a single CSV which will indicate statistics about each program. The intention of this tool is to allow researchers to compare programs against each other and determine where to spend their time.

The tool concept is based on the wonderful [`h1stats` tool by @defparam](https://github.com/defparam/h1stats)

Although I wasn't aware of it at the time I wrote this tool (mostly to learn about Bugcrowd), fyoorer noted their tool which is available [on Github](https://github.com/fyoorer/bcstats) - I haven't tried but the code looks better, feel free to use whichever you like!

**Important** Bugcrowd private program is PRIVATE TO YOU and disclosure of any non-public data *will* violate the NDA you signed. Do not ever share private program information, including in any contribution to this project. This tool should not be used to violate any applicable NDA or legal agreement and is not endorsed by Bugcrowd in any way. The author disclaims any liability related to use of this tool.

## Installation

The tool is a simple Python package. It requires the BS4 parser, which can be installed if you don't already have it by:

```
pip install -r requirements.txt
```

## WARNING

***THIS SCRIPT HANDLES YOUR BUGCROWD SESSION TOKEN WHICH CONTAINS YOUR BUGCROWD PRIVATE DATA AND THE PRIVATE DATA OF YOUR BUGCROWD PROGRAMS. BECAREFUL WHEN HANDLING THIS TOKEN. THE AUTHORS ARE NOT LIABLE FOR ANY MISUSE OF THIS SCRIPT OR YOUR BUGCROWD SESSION TOKEN. PLEASE USE AT YOUR OWN RISK. DO NOT PUBLISH ANY CSVs WITH BUGCROWD NON-PUBLIC PROGRAM DATA.***

## Usage

You will need the value of your `_crowdcontrol_session` cookie which you can acquire from your browser and logged-in session.

Run the tool as follows:
```
export BC_SESSION="<_crowdcontrol_session cookie value>" python -u bcstats -s "${BC_SESSION}"
```

The tool will generate a CSV in the current directory with today's date and the following columns:

 * Program Code
 * Program Name
 * Subscribable?
 * Active?
 * Invited?
 * Public/Private
 * URL
 * Reward Range Summary
 * Duplicate Bug Count
 * Unique Bug Count
 * Rewarded Bug Count
 * Average Days to Validate Bug
 * Average Bounty
 * P1-P5 Max Bounties across all targets

## Feedback

Please file issues or reach out on Twitter at `@h1pmnh` for feedback on this tool!
