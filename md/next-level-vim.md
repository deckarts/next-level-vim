# Next Level Vim

It is definitely worth the time it takes to learn text manipulation with the ubiquitous Vi(m) command line text editor. If you only know how to open a file and enter text, edit some text, and especially how to save edited files and exit the program you will be much better off for it. Vim is readily available in nearly all modern Linux distribution (or BSD) terminal emulator shell programs.

Circumstances where you will find it convenient to know Vim nearly always involve tasks running remote shell operations. If you regularly use Secure Shell `$ ssh user@hostname.provider.com` to work with Virtual Private Servers (VPS) or with local vitalization containers then you probably would like to bring along your environment preferences. You can that with Vim also.

## Run time commands

It is through run time command files that your personal preference settings help you to configure bash and Vim to create a veritable Integrated Development Environment (IDE). The first actual Vim setting you're likely going to want is to switch its legacy compatibility (with Vi) mode off. As a super set, everything in Vi is available or improved in Vim and you get more advanced features.

```
" ~/.vimrc 
" ensure that legacy compatibility mode is off
" documentation: http://vimdoc.sourceforge.net/htmldoc/options.html#'compatible'
set nocp
```

Setting legacy compatibility mode to off might not seem like it's doing anything ([and in fact it might not be doing anything](http://vimdoc.sourceforge.net/htmldoc/starting.html#compatible-default)). Vim switches the mode off by implication when it encounters a `.vimrc` file. It may still be important to be explicit. The shorthand "nocp" is synonymous with  "nocompatible," which also works. There are many "[timtowtdi](https://en.wikipedia.org/wiki/There%27s_more_than_one_way_to_do_it)" conveniences you can learn for switching preferences as you work.

The notion of Vim's "modes" is very important to learn about, especially the difference between the very distinct "Normal" and "Insert" modes. Confusion about modes is what trips up most new users. Modes aren't unique to Vim nor were they introduced by Vi. Command mode is so old that it predates the invention of [copy and paste](https://www.npr.org/2020/02/22/808404858/remembering-the-pioneer-behind-your-computers-cut-copy-and-paste-functions) functionality in the 1970s.

### Important modes
* Normal mode
* Insert mode (includes Replace)
* Visual mode
* Command Line, (also Ex Command or Last Line mode)

Use Vimtutor `$ vimtutor` to interactively learn about movement, modes, and running Ex Commands in "Last Line" mode. Then the indispensable productivity operators become:

. (repeat the last edit action)

; (repeat the last motion or movement forward, use "," for backwards)

/ (search document forwards, use "?" for backward)

\* (find next occurrence of the word under the cursor, use "#" for previous occurrence)

~ (toggle case)

% (toggle between opening and closing (), [], and {} which is highly useful for code)

While it's important to commit the operator language of Vim to memory, the challenge is to learn to think like a musician and combine them into key chords so you can play Vim like a piano. That's where there's true power which rivals any modern programmer editor. Plan your edits strategically by mind-mapping rare characters in relation to your cursor position to use motion sequences and accomplish larger edits.

It is common to edit enclosed text wrapped in (single or double) quotes, parentheses, square brackets, or curly braces. You can change or delete the inner text all at once with "ci(" for parentheses etc. Simply match the construct you are dealing with as the last key in your chord. The obvious implication of this is how you can use it to edit code. Just watch out for strings which escape matching special characters.

Using repeat actions is very productive. You can repeat forward motions with the semicolon which works in Visual mode as we.. To select or edit several sentences you can type "v" for visual first followed by "f." and as many semicolons as required. Once everything you want to change is selected, hit the "c" key to have it deleted and get you into Insert mode.

It is also common to delete words with "dw" which can get tedious if you have a way to go and haven't counted the words. Find a boundary and delete, using the dot "." repeat edit action until you've reached the point you want.

this (woo hoo) set of text

wrap

paste

indent

### Use inner word

Inner word editing actions like "ciw" for "change inner word" allows you to position your cursor anywhere within a word, quotes, parentheses, or brackets to affect change to the whole word or words within the construct. This lessens the burden of placing your cursor at the first character. A serious valuable side effect is dot repeat actions also work regardless where your cursor position is.

\z= (spelling suggestions)

tabs and splits

Ctrl-w (window commands)

After your tutoring, the next thing to learn about is marks. Marks allow you to associate a cursor's position with a letter key for recall while editing a file. Set your marks with 'm' plus a letter key and then recall the position with a back tick (or single quote mark) and that key.

Save a position to the letter 'a' typing 'ma' in Normal mode and type '\`a' in Normal mode to jump back to that position from somewhere else, including from a file elsewhere in your project when using capital letter marks. In order for mark navigation between files to work there can only be one mark of a particular capital letter at a time. List a file's marks with the :marks Ex Command anytime.

## Marks and ctags

For similar jumping power throughout your project, [ctags](http://ctags.sourceforge.net) are superbly integrated with Vim. Navigate Vim's :help file links with your cursor in position on a link and Ctrl-] to jump to the link's target. In order to generate original ctags for yourself (and make them available within Vim), you will need to install the ctags utility with your operating system package manager (homebrew, apt, or yum etc.).

The neat thing about running ctags is that the program links code automatically for you. With ctags generated, place your cursor on a method name and jump to its definition with Ctrl-], (the same key sequence as :help file navigation as defined above). Rerun ctags to regenerate the tags file after heavily editing your project files.

Bleeding edge here...

For marks, ctags, and including your own edit positions you can move back and forth through history with Ctrl-o and Ctrl-i.

Editing history is remembered as a jumplist. You can view the jump list with :ju(mplist) Ex Command. Repeat edit actions with the "." dot key in Normal mode. This is extremely powerful when your last action is a key chord that does something more complex. For far more complex edits record a macro for playback. The dot and macro recording capability rivals anything which looks like magic in other editors.

Visual mode.

Registers (Vim's clipboard)

search and replace
perldo for regular expressions
