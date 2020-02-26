# Next Level Vim

It is definitely worth the time it takes to learn basic text manipulation with the ubiquitous Vi(m) command line text editor. If you only know how to open a file and enter text, edit text, and especially how to save edited files and exit the program you will be much better off for it. Count on Vim being readily available in nearly all modern Linux distro (or BSD) terminal emulator shell programs.

Circumstances where you will find it convenient to know Vim nearly always involve tasks running remote shell operations. If you regularly use Secure Shell `$ ssh user@hostname.provider.com` to work Virtual Private Servers (VPS) or in local virtualisation containers then you probably have a plan for bringing your environment preferences along for the ride. You can do so with Vim as well.

## Runtime commands

It is through runtime command files that personalization preference settings can help you to choose Vim for your Integrated Development Environment (IDE). The first actual Vim setting you're likely going to want is to switch its legacy compatibility with Vi off. As a superset of Vi, everything in Vi is available in Vim and you get the addition of Vim's advanced features.

```
" ~/.vimrc 
" ensure that legacy compatibility mode is off
" documentation: http://vimdoc.sourceforge.net/htmldoc/options.html#'compatible'
set nocp
```

Changing the legacy compatibility mode setting to off might not seem like it's doing anything ([and in fact it might not be doing anything](http://vimdoc.sourceforge.net/htmldoc/starting.html#compatible-default)), but it's important that it is, in fact, switched off. Notice that "nocp" is Vim shorthand for "nocompatible," which also works. There are many "[TIMTOWTDI](https://en.wikipedia.org/wiki/There%27s_more_than_one_way_to_do_it)" conveniences in Vim. Use .vimrc for default behavior and shorthand to toggle preferences in real time.

## Editor modes

The notion of "modes" is very important to learn about, especially the difference between very distinct "Normal" and "Insert" modes. Confusing modes is what trips up most new users. Modes aren't unique to Vim, nor were they introduced by Vi. Command mode is so old that it predates the invention of [copy and paste](https://www.npr.org/2020/02/22/808404858/remembering-the-pioneer-behind-your-computers-cut-copy-and-paste-functions) functionality in the 1970s.

### Important modes
* Normal
* Insert (includes Replace)
* Visual
* Ex Command (or Last Line)

Use Vimtutor `$ vimtutor` to learn about movement, modes, and running Ex Commands in "Last Line" mode. After your tutoring, the next thing to learn about is marks. Marks allow you to associate a cursor's position with a letter key for recall while editing a file. Set your marks with 'm' plus a letter key and then recall the position with a back tick (or single quote mark) and that key.

Save a position to the letter 'a' typing 'ma' in Normal mode and type '\`a' in Normal mode to jump back to that position from somewhere else, including from a file elsewhere in your project when using capital letter marks. In order for mark navigation between files to work there can only be one mark of a particular capital letter at a time. List a file's marks with the :marks Ex Command anytime.

For similar jumping power throughout your project, [ctags](http://ctags.sourceforge.net) are superbly integrated with Vim. Navigate Vim's :help file links with your cursor in position on a link and Ctrl-] to jump to the link's target. In order to generate original ctags for yourself (and make them available within Vim), you will need to install the ctags utility with your operating system package manager (homebrew, apt, or yum etc.).

The neat thing about running ctags is that the program links code automatically for you. With ctags generated, place your cursor on a method name and jump to its definition with Ctrl-], (the same key sequence as :help file navigation as defined above). Rerun ctags to regenerate the tags file after heavily editing your project files.


Bleeding edge here...

For marks, ctags, and including your own edit positions you can move back and forth through history with Ctrl-o and Ctrl-i.

Editing history is remembered as a jumplist. You can view the jump list with :ju(mplist) Ex Command. Repeat edit actions with the "." dot key in Normal mode. This is extremely powerful when your last action is a key chord that does something more complex. For far more complex edits record a macro for playback. The dot and macro recording capability rivals anything which looks like magic in other editors.

Visual mode.

tabs and splits

semicolon to next 

search
search and replace
perldo for regular expressions

wrap

paste

indent
