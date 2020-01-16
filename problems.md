[Click here for General Problems](#general-problems)
[Click here for Windows Problems](#windows-problems)
[Click here for Mac Problems](#mac-problems)

# <a name="general-problems"></a>General problems

## Problem: You get an error message when trying to clone in Atom
Try using git on the command lines as follows. 

1. `Packages -> platform-ide-terminal -> New Terminal`

2. In the terminal that pops up, type `pwd`. This will tell you what directory (folder) you are in. 

3. You want to be in the directory (folder) where you want to keep your problem sets, so you need to find out the **path** to that directory. These website will tell you several ways to do this in [Mac OS](https://www.switchingtomac.com/tutorials/osx/5-ways-to-reveal-the-path-of-a-file-on-macos/) and in [Windows](https://www.thewindowsclub.com/path-copy-copy-lets-you-copy-file-paths). On my Mac, the path to where I keep problem sets for this class is `/Users/emilypx/Desktop/CSCI-1102-S20/ProblemSets`.

4. Once you know the path to the directory where you want to keep your problem sets, you can navigate to that directory with the `cd` command in the terminal, like this:

``cd /Users/emilypx/Desktop/CSCI-1102-S20/ProblemSets``

5. Now that you are in the right place, you can use git. Go copy the url for your repository, as you should already know how to do. Then in the terminal, type `git clone` followed by that URL, like this:

``git clone https://github.com/BC-CSCI-1102-S20-MWF12/ps1-yourgithubusername.git``

6. You'll most likely be asked to enter your GitHub username and password, and you'll have a clone of your repository. You can then open that folder in Atom, and you'll be ready to go.

## Problem: ``javac: file not found:``
1. First check to make sure you spelled the name of your `.java` file correctly.

2. If it's correct, the you are probably in the wrong directory in your terminal. You want to be in the `src` directory of your problem set repository. To get to the correct directory, first try typing `cd src` in the terminal, then try compiling again. If you don't get an error message, you are all set.

3. If you continued to get a `file not found` error, follow steps 3 and 4 above to navigate to the correct directory (i.e., the `src` directory of your ps1 folder), then try compiling again.

## Problem: ``Error: Could not find or load main class``
1. First check to make sure you typed the command correctly: `java HelloWorld`. 

2. If it's correct, the you are probably in the wrong directory in your terminal. You want to be in the `src` directory of your problem set repository. To get to the correct directory, first try typing `cd src` in the terminal, then try compiling again. If you don't get an error message, you are all set.

3. If you continued to get a `Could not find or load main class` error, follow steps 3 and 4 above to navigate to the correct directory (i.e., the `src` directory of your ps1 folder), then try running again.

## Problem: You get an error message when trying to push in Atom
You staged your changes and committed your changes, but you get an error when you click "Push". Try using git on the command lines as follows. 

1. You already have compiled and run your program, so you already have a terminal open to the right place. If you don't, then you'll need to open a new platform-ide-terminal and navigate to your repo. These websites will tell you several ways to find the path to a directory in [Mac OS](https://www.switchingtomac.com/tutorials/osx/5-ways-to-reveal-the-path-of-a-file-on-macos/) and in [Windows](https://www.thewindowsclub.com/path-copy-copy-lets-you-copy-file-paths).

4. Once you know the path to the directory where you want to keep your problem sets, you can navigate to that directory with the `cd` command in the terminal

``cd /The/Path/To/Your/Repo``

5. Now that you are in the right place, you can use git. Type `git push` in the terminal:

``git push``

6. You might be asked to enter your GitHub username and password, and you'll have a clone of your repository. You can then log into GitHub on the web in a browser to make sure that your changes were pushed correctly.

# <a name="windows-problems"></a>Windows problems (For Mac problems, see below)

## Problem: " 'javac' is not recognized as an internal or external command " (*new and improved directions!*)

1. Delete *all* copies of Java from your computer by using the [special Java uninstall tool for Windows here](https://www.java.com/en/download/help/uninstall_java.xml).


2. Determine whether you have 64 bit (x64)or 32 bit (x86) Windows by following [the directions for Windows 10 here](https://www.wikihow.com/Check-if-Your-Computer-Is-64-Bit).


3. [Download the SDK (make sure it’s the SDK!) from here again](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) making sure to select x64 or x86 depending on your results from step 2. Do not try to change the location Java gets installed to. Just let the installer put Java where it likes.

4. Quit any cmd terminals you have open, and quit Atom.

5. Make sure that you have the path to the Java sdk bin directory *exactly* right as follows: (a) navigate in your file system (using Explorer, or whatever it’s called in Windows) to the location where the Java `bin` folder was installed (e.g., `C:\Program Files\Java\jdk1.8.0_201\bin`). **MAKE SURE IT'S JDK and not JRE!!!** (b) Right-click on the `\bin` fodler and choose `Properties`. (c) The path is shown next to the Location header, which you must now highlight and copy.

6. Open your environment variables as described in the problem set, and if you see a JAVA_HOME variable in your environment variables, delete it.

7. Look at the PATH variable. If you see any entry with the word "java" or "Java" or "jre" in it anywhere at all, delete that entry.

8. Add a new entry to the path variable. Paste in what you copied in step 5. If it does not end in `\bin` then add `\bin` to the end, e.g., `C:\Program Files\Java\jdk1.8.0_201\bin`. Make sure it has `\bin`. Make sure it does not have `jre` in it. Onyl `jdk` will work.

9. Launch a cmd terminal and type the `javac -version` and `java -version` commnands to confirm installation.



## Problem: "Please tell me who you are" when trying to push to GitHub

In theory, Atom comes with full git support, but it appears it might not be working for some Windows users. Here are some instructions that I found on the web.

1. Quit Atom.

2. Install git from here: https://git-scm.com/downloads

3. Go to cmd, as you know how to do.

4. Type the following but replace `youremailaddress@bc.edu` with your actual email address.

```bash
git config --global user.email "youremailaddress@bc.edu"
```

5. If that works, then type the following but replace `Your Name` with your name.

```bash
git config --global user.name “Your Name”
```

6. Relaunch Atom and try pushing your changes again. 

If steps 4, 5, or 6 did not work, just use the [GitHub Desktop app](https://desktop.github.com).

---

# <a name="mac-problems"></a>Mac OSX Problems
## Problem: "unable to push, error 403"
This usually means that your credentials have not been entered or are incorrect. Here's one possible way to try to deal with this:

1. Open your ps1 directory in Atom as described in the problem set, then go to `Packages -> platformio-ide-terminal -> New Terminal`.

2. In the little terminal window that opens up, type the following

```bash
git commit -m "making changes"
```

3. Then type

```bash
git push
```

4. If all goes well, you will be asked for your GitHub username and password. You can enter them, and in theory, you won't have to enter them again.

If this does not help, just use the [GitHub Desktop app](https://desktop.github.com).


## Problem: "unable to find remote helper for https"

The issue is often that there is a missing dependency for git that arose in a recent OSX update. If you got a lot of chat from your computer about Xcode or developer tools, it was probably your operating system trying to get that missing dependency for you. Here are some possible solutions. (Remember to quit Atom before trying anything.) Here's a way to try to deal with this:

1. open a Terminal, and type the following:

```bash
xcode-select --install
```

2. In the window that pops up, select `Install` and continue to follow the prompts. (Note that this might take a long time!)

If this does not help, just use the [GitHub Desktop app](https://desktop.github.com).

## Problem: You already have a different version of Java installed

1. Open a Terminal

2. Type these two commands

```bash
cd /Library/Java/JavaVirtualMachines
ls
```
3. You'll see multiple version of the Java sdk. Navigate into the `Contents` directory in the version you don't want to use using `cd`, e.g.,

```bash
cd jdk-10.0.1.jdk/Contents
```

4. Rename `Info.plist` to `Info.plist.disabled`, like this:

```bash
mv Info.plist Info.plist.disabled
```

# Problem with GitHub Classroom: "GitHub repository could not be created. Please try again"

Some ideas:

1. Reboot your computer.

2. Try another browser (e.g., FireFox).

3. Make sure you're connected to BC's wifi network and not some other network (e.g., tethering to your phone, the wifi at Starbucks).

4. Turn off all VPNs.

5. Clear all website data associated with GitHub anbd GitHub Classroom.

6. Turn off all web browser extensions.
