# Next Level Vim

It is definitely worth the time it takes to learn basic text manipulation with the ubiquitous Vi(m) command line text editor. If you only know how to open a file and enter text, edit text, and especially how to save edited files and exit the program you will be much better off for it. Count on Vim being readily available in nearly all modern Linux distro (or BSD) terminal emulator shells.

Vim (Vi "improved") and the excellent Vimtutor programs are often readily available at the command prompt through your default shell PATH variable. Type "echo $PATH" and see. If not, make sure Vim is installed in the first place or install it (which also installs Vimtutor). Make sure the executable binary location is in your PATH and utilize the "export" built-in utility if not.

Circumstances where you will find it convenient to know Vim nearly always involve tasks running remote shell operations. If you regularly use Secure Shell ($ ssh) to work on a Virtual Private Server (VPS) or in a local virtualisation container then you should bring your preferences along for the ride. Edit your shell "runtime commands" file (~/.bashrc) for the export statement and so that your editing default to Vim:

```
# ~/.bashrc (or alternatively) ~/.bash_profile
# set default editor to Vim
export EDITOR=vim
```

Apple's Darwin (FreeBSD) recently switched terminal emulator shells from bash to zsh "Z" shell):

```
#  ~/.zshrc (or alternatively) ~/.zprofile
# set default editor to Vim
export EDITOR=vim
```

It is through these files that personalization preferences with Vim become appealing as a choice for your Integrated Development Environment (IDE). A newly installed Vim may be limited to backward compatibility with legacy Vi. The first actual Vim setting you're likely going to want is switch its legacy compatibility with Vi off. That way, you are sure to have access to Vim's advanced features:

```
" ~/.vimrc 
" ensure that legacy compatibility mode is off
" documentation: http://vimdoc.sourceforge.net/htmldoc/options.html#'compatible'
set nocp
```

As a superset, everything available in Vi is available in Vim. Vim adds advanced features that you're going to want. Changing the legacy compatibility mode setting to off might not seem like it's doing anything ([and in fact it might not be doing anything](http://vimdoc.sourceforge.net/htmldoc/starting.html#compatible-default)), but it's important that it is, in fact, switched off. Take notice that "nocp" is Vim shorthand for "nocompatible," which also works. There are many shorthand conveniences in Vim.

The notion of "modes" is very important to learn about, especially the difference between very distinct "Normal" and "Insert" modes. Confusing modes is what trips up most new users. Modes aren't unique to Vim, nor were they introduced by Vi. Command modes predate the invention of [copy and paste](https://www.npr.org/2020/02/22/808404858/remembering-the-pioneer-behind-your-computers-cut-copy-and-paste-functions) functionality in the 1970s.

Important modes
* Normal
* Insert (includes Replace)
* Visual
* Ex Command (or Last Line)

Use Vimtutor to learn about modes and for running ex commands in "Last Line" mode. After your tutoring, the next thing to learn about is marks. Marks allow you to associate a cursor's position with a letter key for later recall. Set your marks with 'm' plus a key and then recall it with a back tick (or single quote mark) and that key.

Save a position to the letter 'a' typing 'ma' in Normal mode and type '\`a' in Normal mode to jump back to that position from somewhere else including from a file elsewhere in your project using capital letter marks. In order for navigation between files to work there can only be one capital mark of a letter at a time. List marks with the :marks Ex Command anytime.

Similarly, [ctags](http://ctags.sourceforge.net) are superbly integrated with Vim. Navigate Vim's :help file links with your cursor in position and Ctrl-] to jump to the link target. In order to generate original ctags for yourself (and make them available within Vim), you will need to install the ctags utility with your operating system package manager (homebrew, apt, or yum etc.).

The neat thing about running ctags is that it links code automatically for you. With ctags generated, place your cursor on a method name and jump to its definition with Ctrl-], (the same key sequence as :help file navigation as defined above). Rerun ctags to regenerate the tags file after heavily editing your project files.

Bleeding edge here...

For marks, ctags, and including your own edit positions you can move back and forth through history with Ctrl-o and Ctrl-i.

Editing history is also remembered. Repeat edit actions with the "." dot key in Normal mode. This is extremely powerful when your last action is a key chord that does something more complex. For far more complex edits record a macro for playback. The dot and macro recording capability rivals anything which looks like magic in other editors.

Visual mode.

semicolon to next 

search
search and replace
perldo for regular expressions

wrap

paste

indent
