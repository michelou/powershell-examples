# <span id="top">Playing with PowerShell on Windows</span>

<table style="font-family:Helvetica,Arial;line-height:1.6;">
  <tr>
  <td style="border:0;padding:0 10px 0 0;min-width:25%;"><a href="https://www.powershell.org/" rel="external"><img src="./docs/images/PowerShell_5.0_icon.png" width="120" alt="PowerShell project"/></a></td>
  <td style="border:0;padding:0;vertical-align:text-top;">This repository gathers <a href="https://www.powershell.org/" rel="external">PowerShell</a> code examples coming from various websites and books.<br/>
  It also includes several build scripts (<a href="https://www.gnu.org/software/bash/manual/bash.html" rel="external">bash scripts</a>, <a href="https://en.wikibooks.org/wiki/Windows_Batch_Scripting" rel="external">batch files</a>) for experimenting with <a href="https://www.powershell.org/" rel="external">PowerShell</a> on a Windows machine.</td>
  </tr>
</table>

[Ada][ada_examples], [Akka][akka_examples], [C++][cpp_examples], [COBOL][cobol_examples], [Common&nbsp;Lisp][cl_examples], [Component&nbsp;Pascal][component_pascal_examples],  [Dafny][dafny_examples],  [Dart][dart_examples], [Deno][deno_examples], [Docker][docker_examples], [Erlang][erlang_examples], [Flix][flix_examples], [GraalVM][graalvm_examples], [Haskell][haskell_examples], [Kafka][kafka_examples], [Kotlin][kotlin_examples], [LLVM][llvm_examples], [Modula-2][m2_examples], [MySQL][mysql_examples], [Node.js][nodejs_examples], [Rust][rust_examples], [Scala&nbsp;3][scala3_examples], [Spark][spark_examples], [Spring][spring_examples], [Standard&nbsp;ML][sml_examples], [TruffleSqueak][trufflesqueak_examples], [WiX&nbsp;Toolset][wix_examples] and [Zig][zig_examples] are other topics we are continuously monitoring.

## <span id="proj_deps">Project dependencies</span>

This project depends on the following external software for the **Microsoft Windows** platform:

- [Git 2.54][git_downloads] ([*release notes*][git_relnotes])
- [PowerShell 7.6 LTS][powershell_downloads] ([*release notes*][powershell_relnotes], [*what's new*][powershell_whatsnew])

Optionally one may also install the following software:

- [ConEmu 2023][conemu_downloads] ([*release notes*][conemu_relnotes])
- [Visual Studio Code 1.125][vscode_downloads] ([*release notes*][vscode_relnotes])

For instance our development environment looks as follows (*June 2026*) <sup id="anchor_01">[1](#footnote_01)</sup>:

<pre style="font-size:80%;">
C:\opt\ConEmu\                  <i>( 26 MB)</i>
C:\opt\Git\                     <i>(390 MB)</i>
C:\opt\VSCode\                  <i>(793 MB)</i>
C:\Program Files\PowerShell\7\  <i>(282 MB)</i>
</pre>

## <span id="structure">Directory structure</span> [**&#x25B4;**](#top)

This project has the following directory structure :

<pre style="font-size:80%;">
docs\{<a href="./docs/MODULES.md">MODULES.md</a>, <a href="./docs/POLICIES.md">POLICIES.md</a>, ...}
examples\{<a href="./examples/README.md">README.md</a>, <a href="./examples/hello/">hello</a>, ...}
<a href="README.md">README.md</a>
<a href="RESOURCES.md">RESOURCES.md</a>
<a href="setenv.bat">setenv.bat</a>
</pre>

where

- directory [**`docs\`**](docs/) contains [PowerShell] related papers/articles.
- directory [**`examples\`**](examples/) contains [PowerShell] code examples.
- file [**`README.md`**](README.md) is the [Markdown][github_markdown] document for this page.
- file [**`RESOURCES.md`**](RESOURCES.md) gathers [PowerShell] related documents.
- file [**`setenv.bat`**](setenv.bat) is the batch script for setting up our environment.


## <span id="commands">Batch commands</span> [**&#x25B4;**](#top)

### **`setenv.bat`** <sup id="anchor_02">[2](#footnote_02)</sup>

We execute command [**`setenv.bat`**](setenv.bat) once to setup our development environment; it makes external tools such as [**`code.cmd`**][code_cli] and [**`git.exe`**][git_cli] directly available from the command prompt.

<pre style="font-size:80%;">
<b>&gt; <a href="setenv.bat">setenv</a></b>
Tool versions:
   code 1.125.1, powershell 5.1.26100.7920, pwsh 7.6.3,
   git 2.54.0, diff 3.12, bash 5.3.9(1)

<b>&gt; <a href="https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/where_1" rel="external">where</a> code git pwsh</b>
C:\opt\VSCode\bin\code
C:\opt\VSCode\bin\code.cmd
C:\opt\Git\bin\git.exe
C:\Program Files\PowerShell\7\pwsh.exe
</pre>

<!--=======================================================================-->

## <span id="footnotes">Footnotes</span> [**&#x25B4;**](#top)

<span id="footnote_01">[1]</span> ***Downloads*** [↩](#anchor_01)

<dl><dd>
In our case we downloaded the following installation files (see <a href="#proj_deps">section 1</a>):
</dd>
<dd>
<pre style="font-size:80%;">
<a href="https://github.com/Maximus5/ConEmu/releases/tag/v23.07.24" rel="external">ConEmuPack.230724.7z</a>              <i>(  5 MB)</i>
<a href="https://git-scm.com/download/win" rel="external">PortableGit-2.54.0-64-bit.7z.exe</a>  <i>( 41 MB)</i>
<a href="https://github.com/PowerShell/PowerShell/releases/tag/v7.6.3" rel="external">PowerShell-7.6.3-win-x64.msi</a>      <i>(111 MB)</i>
<a href="https://code.visualstudio.com/Download#" rel="external">VSCode-win32-x64-1.125.1.zip</a>      <i>(131 MB)</i>
</pre>
</dd></dl>

<span id="footnote_02">[2]</span> **`setenv.bat` *usage*** [↩](#anchor_02)

<dl><dd>
Batch file <a href=./setenv.bat><code><b>setenv.bat</b></code></a> has specific environment variables set that enable us to use command-line developer tools more easily.
</dd>
<dd>It is similar to the setup scripts described on the page <a href="https://learn.microsoft.com/en-us/visualstudio/ide/reference/command-prompt-powershell" rel="external">"Visual Studio Developer Command Prompt and Developer PowerShell"</a> of the <a href="https://learn.microsoft.com/en-us/visualstudio/windows" rel="external">Visual Studio</a> online documentation.
</dd>
<dd>
For instance we can quickly check that the two scripts <code>Launch-VsDevShell.ps1</code> and <code>VsDevCmd.bat</code> are indeed available in our Visual Studio 2019 installation :
<pre style="font-size:80%;">
<b>&gt; <a href="https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/where" rel="external">where</a> /r "C:\Program Files (x86)\Microsoft Visual Studio" *vsdev*</b>
C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\Launch-VsDevShell.ps1
C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\VsDevCmd.bat
C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\vsdevcmd\core\vsdevcmd_end.bat
C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\Tools\vsdevcmd\core\vsdevcmd_start.bat
</pre>
</dd>
<dd>
Concretely, in our GitHub projects which depend on Visual Studio (e.g. <a href="https://github.com/michelou/cpp-examples"><code>michelou/cpp-examples</code></a>), <a href="./setenv.bat"><code>setenv.bat</code></a> does invoke <code>VsDevCmd.bat</code> (resp. <code>vcvarall.bat</code> for older Visual Studio versions) to setup the Visual Studio tools on the command prompt. 
</dd></dl>

***

*[mics](https://lampwww.epfl.ch/~michelou/)/June 2026* [**&#9650;**](#top)
<span id="bottom">&nbsp;</span>

<!-- link refs -->

[ada_examples]: https://github.com/michelou/ada-examples#top
[akka_examples]: https://github.com/michelou/akka-examples#top
[cl_examples]: https://github.com/michelou/cl-examples#top
[cobol_examples]: https://github.com/michelou/cobol-examples#top
[code_cli]: https://code.visualstudio.com/docs/editor/command-line
[component_pascal_examples]: https://github.com/michelou/component-pascal-examples#top
[conemu_downloads]: https://github.com/Maximus5/ConEmu/releases
[conemu_relnotes]: https://conemu.github.io/blog/2023/07/24/Build-230724.html
[cpp_examples]: https://github.com/michelou/cpp-examples#top
[dafny_examples]: https://github.com/michelou/dafny-examples#top
[dart_examples]: https://github.com/michelou/dart-examples#top
[deno_examples]: https://github.com/michelou/deno-examples#top
[docker_examples]: https://github.com/michelou/docker-examples#top
[diff_cli]: https://www.gnu.org/software/diffutils/manual/html_node/Invoking-diff.html
[erlang_examples]: https://github.com/michelou/erlang-examples#top
[flix_examples]: https://github.com/michelou/flix-examples#top
[git_cli]: https://git-scm.com/docs/git
[git_downloads]: https://git-scm.com/download/win
[git_exe]: https://git-scm.com/docs/git
[git_relnotes]: https://raw.githubusercontent.com/git/git/master/Documentation/RelNotes/2.54.0.adoc
[github_markdown]: https://github.github.com/gfm/
[golang]: https://golang.org/
[golang_downloads]: https://golang.org/dl/#stable
[golang_relnotes]: https://golang.org/doc/devel/release.html#go1.24
[graalvm_examples]: https://github.com/michelou/graalvm-examples#top
[haskell_examples]: https://github.com/michelou/haskell-examples#top
[kafka_examples]: https://github.com/michelou/kafka-examples#top
[kotlin_examples]: https://github.com/michelou/kotlin-examples#top
[llvm_examples]: https://github.com/michelou/llvm-examples#top
[m2_examples]: https://github.com/michelou/m2-examples#top
[msys2_changelog]: https://github.com/msys2/setup-msys2/blob/main/CHANGELOG.md
[msys2_downloads]: http://repo.msys2.org/distrib/x86_64/
[mysql_examples]: https://github.com/michelou/mysql-examples#top
[nodejs_examples]: https://github.com/michelou/nodejs-examples#top
[powershell_downloads]: https://github.com/PowerShell/PowerShell/releases/tag/v7.6.3
[powershell_relnotes]: https://github.com/PowerShell/PowerShell/releases/tag/v7.6.3
[powershell_whatsnew]: https://learn.microsoft.com/en-us/powershell/scripting/whats-new/what-s-new-in-powershell-76
[rust_examples]: https://github.com/michelou/rust-examples#top
[scala3_examples]: https://github.com/michelou/dotty-examples#top
[sml_examples]: https://github.com/michelou/sml-examples#top
[spark_examples]: https://github.com/michelou/spark-examples#top
[spring_examples]: https://github.com/michelou/spring-examples#top
[trufflesqueak_examples]: https://github.com/michelou/trufflesqueak-examples#top
[vscode_downloads]: https://code.visualstudio.com/#alt-downloads
[vscode_relnotes]: https://code.visualstudio.com/updates/
[wix_examples]: https://github.com/michelou/wix-examples#top
[zig_examples]: https://github.com/michelou/zig-examples#top
