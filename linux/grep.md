# linux三剑客之grep

**grep是linux中一个强大的文本搜索工具，它使用正则表达式搜索文本，并把匹配的行打印出来**

**grep的全称是Global Regular  Expression Print**

**意思是全局正则表达式版本，它的使用权是所有用户**

---

### NAME(grep的别名)

> grep，egrep，fgrep，rgrep 	
>
> print lines that match patterns(打印与模式匹配的行)

### SYNOPSIS(简介)

> grep [OPTION...] PATTERNS ... [FILE...]
>
> grep [OPTION...] -e PATTERNS ... [FILE...]
>
> grep [OPTION...] -f PATTERNS_FILE ... [FILE]
>
> PS：OPTION(选项)   PATTERNS(模式) FILE(文件)

### DESCRIPTION(说明)

> grep searches for PATTERNS in each FILE. 	PATTERNS is one or more patterns separated by newline characters, and grep prints each line that matches a pattern.	Typically PATTERNS should be quoted when grep is used in a shell command
>
> > grep在每个文件中进行PATTERNS的搜索，PATTERNS是由换行符进行分隔一个或多个进行的，之后grep打印出与PATTERNS匹配的每一行，通常在shell命令中使用grep，应该将PATTERNS应用起来引号引起来。
>
> A FILE of "-" stands for standard input. If no FILE is given, recursive searches examine the working directory, and nonrecursive searches read standard input.
>
> > "-" 代表文件的引入标准，如果为提供要引入的文件，则递归检查工作目录，而非递归搜索将读取标准输入
>
> In addition, the variant programs egrep, fgrep, and rgrep are the same as grep -E , grep -F, and grep -r, respectively. These variants are deprecated, but are provided ofr backward compatibility.
>
> > 另外，变体程序egrep，fgrep和rgrep分别于grep -e，grep -f和grep -r相同，这些变体已经弃用，但提供了后续的兼容性

### OPTION(选项)

**Generic Program Information(通用程序信息)**

> --help Output a usage message and exit.(输出使用情况信息并退出)
>
> -V,--version  Output the version number of grep and exit.(输出grep的版本号并退出)

**Pattern Syntax(语法模式)**

> -E,--extended-regexp  nterpret PATTERNS as extended regular expressions (EREs, see below).(将模式解释为扩展的正则表达式，(EREs,详情见下文))
>
> -F,fixed-strings  Interpret PATTERNS as fixed strings, not regular expressions.(将模式解释为固定字符串，而不是正则表达式)
>
> -G,--basic-regexp	Interpret PATTERNS as basic regular expressions (BREs, see below). This is the default.(将模式解释为基本正则表达式，(BREs,详情见下文)，这是默认值)
>
> -P, --perl-regexp	Interpret PATTERNS as Perl-compatible regular expressions (PCRES). This option is experimental when combined with the -z (--null-data) option, and grep -P may warn of unimplemented features.(将模式解释为与Perl兼容的正则表达式(PCRES)。与-z (--null-data)选项结合使用时，因为此选项时实验阶段，可能会警告未实现此功能)

**Matching Control(匹配控制)**

> -e PATTERNS,	--regexp=PATTERNS
>
> > Use PATTERNS as the patterns.	If this option is used multiple times or is combined with the -f(--file) option, search for all patterns given.  This option can be used to protect a pattern beginning with "-"
> >
> > > 选择使用的模式。如果此选项多次使用或与-f(--file)选项结合使用，请搜索给定的所有模式。此选项可用于保护以"-"开头的模式
>
> -f FILE,	--file=FILE
>
> > Obtain patterns from FILE, one per line. If this option is used multiple times or is combined with the -e(--regexp) option, search for all patterns given. The empaty file contains zero patterns, and therefore matches onthing.
> >
> > > 从FILE中获取模式，每行一个。 如果此选项多次使用或与-e（-regexp）选项结合使用，则搜索给定的所有模式。 Empaty文件包含零个模式，因此与其他内容匹配。
>
> -i,	--ignore-case
>
> > Ignore case distinctions in patterns and input data, so that characters that differ only in case match eache other.
> >
> > > 忽略模式和输入数据中的大小写区别，以便仅大小写不同的字符彼此匹配。 
>
> --no-ignore-case
>
> > Do not ignore case distinctions in patterns and input data. This is the default. This option is usefule for passing to shell scripts that already use -i, to cancel its effects because the two options override each other.
> >
> > > 不要忽略模式和输入数据中的大小写区别。 这是默认值。 该选项对于传递到已经使用-i的shell脚本以取消其效果很有用，因为这两个选项会相互覆盖。 
>
> -v,	--invert-mathc
>
> > Invert the sense og matching, to select non-matching lines.
> >
> > > 反转匹配，选中不匹配的行
>
> -w,	--word-regexp
>
> > Select only those lines containing matches that form whole words. The test is that the matching substring must either be at the beginning of the line, or preceded by a non-word constituent character. Similarly, it must be either at the end of the line or followed by a non-word constituent character Word-constituent characters are letters, digits, and the underscore. This option has no effect if -x is also specified.
> >
> > > 仅选择包含构成整个单词的匹配项的行。 测试是匹配的子字符串必须在行的开头，或者在非单词组成字符的前面。 同样，它必须在行的末尾，或者后跟非单词组成字符。单词组成字符是字母，数字和下划线。 如果还指定了-x，则此选项无效。 
>
> -x,	--line-regexp
>
> > Select only those matches that exactly match the whole line. For a regular expression pattern, this is like parenthesizing the pattern and the surrounding it with ^ and $.
> >
> > > 仅选择与整行完全匹配的那些匹配项。 对于正则表达式模式，这就像将模式括起来并用^和$括起来。
>
> -y 
>
> > Obsolete synonym for -i.
> >
> > > -i的过时同义词。 

**General Output Control(通用输出控制)**



