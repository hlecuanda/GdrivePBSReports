# GdrivePBSReports
Text printer report processing shim for PBS installations on Linux/UNIX.

## Requirements Spec
  - Mimic a spooled UNIX printer, reading plain text on *stdin*.
  - Parses the first 10 lines from input, to determine report identity.
  - Loads the appropriate report model class, instantiated with the rest of input stream.
  - If no report model class is found for the identified report, log the incident, skip parsing and just forward *stdin* to *stdout*.
  - Parses the report instance.
    - Discard blank lines.
    - Discard page headers and footers.
    - Compress multi-line records to single lines.
  - Creates a Google Sheets document and stores parsed data in cells, according to specific report model.
  - Google Sheets Document stored in Google Drive as [Module]-[ReportName][ReportDate]-[ReportNumber], v.gr: 
    - IC-IventoryValuationByDate-20150502-1234
    - AP-Aging-20150502-1235
    - GL-JournalsEditList-20150502-1236.
  - Forwards untouched *stdin* to *stdout* (This should ideally be a unix printing command, for clarity on the PBS config file and printer definition).
  - Optionally modify output conforming to a custom report format template.
    - Store output as PDF to a specified directory for archival or serving via web or other means.
  - Optionally stores data on a SQL database for further BI analysis with external tools.
  - Optionally use a command line option to specify print command.

If that didn't make any sense, this software is probably useless to you, sorry.

## Status
This is pre-pre alpha experimental software in development. 

It's probably based on bad ideas, and poorly implemented. 

Using this software is *not* recommended and may cause your PBS installation to halt and catch fire. 

Reading the source code is a health hazard with known side effects such as uncontrollable rage; early onset Tourette's syndrome in varied languages not limited to english, german and spanish; and migraine headaches. 

You've been warned.

Stuff happens on the devel branch.

[![Analytics](https://ga-beacon.appspot.com/UA-26756841-3/GdrivePBSReports/Master)](https://github.com/igrigorik/ga-beacon?flat)
