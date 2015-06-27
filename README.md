# GdrivePBSReports
Text printer report processing shim for PBS installations on Linux/UNIX

## Requirements Spec
  - Mimic a spooled UNIX printer, reading plain text on *stdin*.
  - Parses the first 10 lines from input, to determine report identity
  - Loads the appropriate report model class, instantiated with the rest of input stream
  - Parses the report, optionally storing data on a SQL database for further BI analysis with external tools
  - Creates a Google Sheets document and stores parsed data in cells, according to specific report model
  - Forwards untouched *stdin* to *stdout* (This should ideally be a unix printing command, for clarity on the PBS config file and printer definition)
  - Optionally use a command line option to specify print command

## Status
This is pre-pre alpha experimental software in development. It's probably based on bad ideas, and it's surely implemented poorly. Using this software is *not* recommended and may cause your PBS installation to halt and catch fire. Reading the code is a health hazard with known side effects as uncontrollable rage, early onset tourette's syndrome in varied languages not limited to english, german and spanish; and migraine headaches. You've been warned.

Stuff happens on the devel branch.

[![Analytics](https://ga-beacon.appspot.com/UA-26756841-3/GdrivePBSReports/Repo)](https://github.com/igrigorik/ga-beacon?flat)
