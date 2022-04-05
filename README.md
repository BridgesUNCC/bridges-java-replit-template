# Replit Java Template for Bridges

This is a Replit IDE template for the Bridges Java library that you can use to create assignments for your students.

More information about the Bridges project can be found [here](http://bridgesuncc.github.io/index.html).
The Bridges Java library documentation can be found [here](http://bridgesuncc.github.io/doc/java-api/current/html/index.html).

When the Bridges library is updated, this repository should be updated shortly thereafter (if necessary).

### Getting Started

1. Use the GitHub import feature to use this repository as a template when creating a new repl
2. Insert your assignment scaffolding in the [main file](java_test.java)
3. (Optional) Remove the [readme](README.md), [license](LICENSE.md), and [library setup](replit-java-setup.sh) files
4. Create a project (assignment) from the repl
5. Publish to your students

### Building and Running

Just press the "Run" button. It will automatically compile and run the program.

Replit should automatically switch to the Console tab (to the right of the editor tab), but if it does not, you will have to manually do so to access stdin, stdout, and stderr.

## Notes/FAQ

> Where can I learn more about Replit?

Replit's documentation can be accessed [here](https://docs.replit.com/).
It has resources for teachers [here](https://docs.replit.com/teams-edu/intro-teams-education).

The following resources might be helpful as you are getting started with Replit:

* [How to invite students](https://docs.replit.com/teams-edu/inviting-teachers-students#invite-team-members-students)
* [Turning personal REPLs into assignments](https://docs.replit.com/teams-edu/repls-to-team-projects)
* [Creating lesson plans](https://docs.replit.com/teams-edu/lesson-authoring)
* [Using the autograder](https://docs.replit.com/teams-edu/testing-assessments-autograding)

> What is the difference between the Console and Shell tabs in Replit?

In languages with a supported REPL environment (Python, Ruby, etc.), the Console tab is a REPL and also handles stdin/out/err of your application.
(Not to be confused with a repl, an IDE instance hosted by Replit.
More information on REPLs can be found [here](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop).)

In languages without a REPL environment (C, C++, etc.) or languages with a REPL environment not supported by Replit (e.g. [Java](https://docs.oracle.com/javase/9/jshell/introduction-jshell.htm)), the Console is a Bash shell you can interact with and where stdin/out/err of your application is handled.
However, it is not identical in functionality to the Shell tab, as the Shell tab is a terminal emulator while the Console tab is not.
This difference is not important for many applications, but some, espcially (n)curses-based applications (git, man, vim, etc.) will work as expected in the Shell tab but are unusable in the Console tab.

> There is a new Bridges library available but this repository has not yet been updated. How do I get the latest version?

In the Console or Shell tabs (to the right of the editor tab), execute the following commands:

```sh
curl -O http://bridgesuncc.github.io/sw/replit-java-setup.sh # download latest setup script (overwriting the existing script)
rm -r lib/ # delete existing Bridges library
sh replit-java-setup.sh $(pwd) # run script
```

After this, you will have to manually re-run any Makefile changes.

See the [Using Bridges Java with Repl.it](https://bridgesuncc.github.io/bridges_setup_java_replit.html) guide if this fails.

> I do not want my assignment to be in a file named `java_test.java`. What do I do?

1. Rename `java_test.java` and set the class name in the file to match
2. Either manually edit the [Makefile](Makefile) and [replit](.replit) file or, in the Console or Shell tabs (to the right of the editor tab), execute the following commands:
   ```sh
   sed -i 's/java_test.java/MyNewClassName.java/g' Makefile # update make source file
   sed -i 's/java_test.java/MyNewClassName.java/g' .replit # update default file for Replit to open on startup
   ```

> I need to compile multiple .java files. How do I do that?

Either manually edit the [Makefile](Makefile) or, in the Console or Shell tabs (to the right of the editor tab), execute the following command:

```sh
sed -i 's/java_test.java/java_test.java OtherFile1.java OtherFile2.java Etc.java/g' Makefile # update make source files
```

> I do not want my executable to be named `java_test`. How do I rename it?

Either manually edit the [Makefile](Makefile) or, in the Console or Shell tabs (to the right of the editor tab), execute the following command:

```sh
sed -i 's/EXE=java_test/EXE=MyNewExecutableName/g' Makefile # update make destination file
```

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
