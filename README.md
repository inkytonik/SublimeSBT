SublimeSBT
==========
[SBT](http://www.scala-sbt.org/) build tool integration for
[Sublime Text 2](http://sublimetext.com/2).

SublimeSBT runs SBT as an interactive REPL inside Sublime Text 2's output panel
and highlights compile errors and test failures in the source code.

Installing
----------
Download [Package Control](http://wbond.net/sublime_packages/package_control)
and use the *Package Control: Install Package* command from the command palette.
Using Package Control ensures SublimeSBT will stay up to date automatically.

Using
-----
SublimeSBT is mostly used through the Command Palette. To open the pallete,
press `ctrl+shift+p` (Windows, Linux) or `cmd+shift+p` (OS X). The SublimeSBT
commands are all prefixed with `SBT:`. The commands only show up in the command
palette if SublimeSBT detects that your project is an SBT project.

**Start SBT**

 - Start an SBT session for the current project. If the project looks like a
  Play Framework project, the `play` command is used instead of the `sbt`
  command.

**Stop SBT**

 - Stop the currently running SBT session.

**Kill SBT**

 - Force the currently running SBT session to stop.

**Show SBT Output**

 - Show the SBT output panel if it's not already showing. This also focuses the
  output panel and puts the cursor at the end.

**Compile, Test, Run, Start Console**

 - Run the `compile`, `test`, `run`, or `console` SBT command. If SBT is
  currently running the command is run in interactive mode, otherwise it's run
  in batch mode.

**Start Continuous Compiling, Start Continuous Testing**

 - Run `~ compile` or `~ test`. If SBT is currently running the command is run
  in interactive mode, otherwise it's run in batch mode.

**Clear Errors**

 - Clear any compile errors or test failures and remove any highlighting
  thereof.

Configuring
-----------
The default settings can be viewed by accessing the ***Preferences >
Package Settings > SublimeSBT > Settings – Default*** menu entry. To ensure
settings are not lost when the package is upgraded, make sure all edits are
saved to ***Settings – User***.

**sbt_command**

 - An array representing the command line to use to start sbt. Depending on
  your setup you may need to put the full path to the file here.

**play_command**

 - An array representing the command line to use to start sbt for a Play
  Framework project. Depending on your setup you may need to put the full path
  to the file here.

**color_scheme**

 - The color scheme to use for the output panel. Only the default foreground
  and background colors are used.

Project-specific settings can also be configured by placing them in a
"SublimeSBT" object inside of "settings" in your sublime-project file, e.g.:

    {
        "folders":
        [
            {
                "path": "/Users/jarhart/scalakoansexercises"
            }
        ],
        "settings":
        {
            "SublimeSBT":
            {
                "sbt_command": ["bash", "/Users/jarhart/scalakoansexercises/sbt"]
            }
        }
    }

Contributing
------------

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
