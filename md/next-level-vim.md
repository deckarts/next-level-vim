# Next Level Vim

It is definitely worth the time it takes to learn basic text manipulation with the ubiquitous Vi command line text editor. If you only know how to open a file and enter text, edit text, and especially how to save edited files and exit the program you will be much better off for it. Count on Vi being readily available in nearly all modern Linux distro (or BSD) terminal emulator shells.

More powerful than Vi is knowing Vim (Vi "improved") to any level of mastery. Vim and the excellent Vimtutor programs are usually available at the command prompt as present in your shell PATH variable. Type "echo $PATH" and see. If not, make sure Vim is installed in the first place, which also installs Vimtutor. Make sure the executable binary location is in your PATH and use the "export" utility if not.

Circumstances where you will find it convenient to know Vi(m) nearly always involve tasks running remote shell operations. If you regularly use Secure Shell ($ ssh) to work on a Virtual Private Server (VPS) or in a local virtualisation container then you should bring your preferences along for the ride. Edit your shell "runtime commands" file (~/.bashrc) for the export statement and so that edits default to Vim:

```
# ~/.bashrc (or alternatively) ~/.bash_profile
# set default editor to Vim
export EDITOR=vim
```

Apple's Darwin (FreeBSD) recently switched default terminal emulator shell from bash to zsh "Z" shell):

```
#  ~/.zshrc (or alternatively) ~/.zprofile
# set default editor to Vim
export EDITOR=vim
```

It is through these files that personalization preferences with Vim become appealing as a choice for your Integrated Development Environment (IDE). A newly installed Vim may be limited to backward compatibility with legacy Vi. The first actual Vim setting you're likely going to want is to switch is its legacy compatibility with Vi. That way, you are sure to have access to Vim's advanced features:

```
" ~/.vimrc 
" ensure that legacy compatibility mode is off
" documentation: http://vimdoc.sourceforge.net/htmldoc/options.html#'compatible'
set nocp
```

Vi has limitations that your copy of Vim will now bypass in favor of its advanced features. Changing the setting might not seem like it's doing anything ([in fact it might not be doing anything](http://vimdoc.sourceforge.net/htmldoc/starting.html#compatible-default)), but it's important that legacy mode is, in fact, switched off. Think of "nocp" as Vim shorthand for "nocompatible," which also works.

Important modes
* Normal
* Insert (includes Replace)
* Visual
* Ex (or Last Line)

The notion of "modes" is very important to learn about with Vim, especially the difference between the very distinct "Normal" and "Insert" modes. Confusing Vim's modes are what will trip up most new users. Modes aren't unique to Vim, nor were they introduced by Vi. Command modes were necessary for the invention of [copy and paste](https://one.npr.org/i/808404858:808404859) functionality.

Use Vimtutor to learn about modes and running ex commands in "Last Line" mode. After your tutoring the next thing to learn about is marks. Marks allow you to associate a cursor's position with a letter key for later recall. Set your marks with ‘m' plus a key and then recall it with a back tick (or single quote mark) and that key.

Save a position to the letter ‘a' typing ‘ma' in Normal mode and type ‘\`a' in Normal mode to jump back to that position from somewhere else, including files elsewhere in your project. If a mark doesn't seem to work chances are that you've removed the text delineating that mark position. Just get started marking and list your marks with :marks anytime you want.

Tip: I like to save the (number) letter 1 to my latest progress point. The 1 key is nearby back tick for easy recall.

Similarly, [ctags](http://ctags.sourceforge.net) are superbly integrated with Vim. Navigate Vim's :help file links with your cursor in position and Ctrl-]. To generate original ctags for yourself (and make them available within Vim), you will need to install the ctags utility with your operating system package manager (homebrew, apt, or yum etc.).

The neat thing about running ctags is that it links code automatically for you automatically. With ctags generated, place your cursor on a method name and jump to its definition with Ctrl-], (the same key sequence as :help file navigation). Rerun ctags to regenerate the tags file after heavily editing your project files.

For marks, ctags, and including your own edit positions you can move back and forth through history with Ctrl-o and Ctrl-i.

Editing history is also remembered. Repeat edit actions with the "." dot key in Normal mode. This is extremely powerful when your last action is a key chord that does something more complex. For far more complex edits record a macro for playback. The dot and macro recording capability rivals anything which looks like magic in other editors.

Visual mode.
