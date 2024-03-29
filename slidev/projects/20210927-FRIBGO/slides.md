---
theme: default
background: https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/frib-building.jpg?raw=true
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  # FRIBGO weekly presentation

  - Source code: <a href="https://github.com/Fanurs/myself/tree/main/slidev/projects/20210927-FRIBGO" title="20210927-FRIBGO"><img class="inline-block h-8 bg-white" src="https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg"/></a>
  - GitHub Pages: <a href="https://fanurs.github.io/myself/" title="Fanurs/myself"><img class="inline-block h-8 bg-white" src="https://github.githubassets.com/images/modules/logos_page/Octocat.png"/></a>
drawings:
  persist: false
title: Modern ROOT
layout: cover
---

# Modern ROOT

A better coding experience for nuclear physicists

<br><br>

Fanurs C.E. Teh<br>
September 27, 2021 (Mon)

<br>

<center>
  <img src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/cern-root-logo.png?raw=true" width="400" style="background-color: #FFFA;"/>
</center>

<a class="absolute right-5 bottom-5 text-xs" href="https://commons.wikimedia.org/wiki/File:FRIB_southeast_view.jpg" target="_blank">
  https://commons.wikimedia.org/wiki/File:FRIB_southeast_view.jpg
</a>

---

# This talk is *not* about...

<div class="grid grid-cols-2 gap-x-2 gap-y-10">

<v-clicks :every="2">

- ~~A comprehensive ROOT tutorial~~

<div>
  <a class="text-xs" href="https://root.cern/get_started/" target="_blank">
    https://root.cern/get_started/
  </a>
  <iframe class="container" src="https://root.cern/get_started/"></iframe>
</div>

- ~~Advertising ROOT as the best analysis tool for nuclear physicists~~

<div class="grid grid-cols-4 gap-x-0 gap-y-2 place-items-center">
  <img class="h-20 rounded bg-white" src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/conda-small-logo.png?raw=true"/>
  <img class="h-20 rounded bg-white" src="https://avatars.githubusercontent.com/u/1525981?s=200&v=4"/>
  <img class="h-20 rounded bg-white" src="https://media.githubusercontent.com/media/microsoft/vscode-docs/69aa119cd341268a1368980a4e40ab7c5a2964a4/images/logo-stable.png"/>
  <img class="h-20 rounded bg-white" src="https://avatars.githubusercontent.com/u/7388996?s=200&v=4"/>
  <img class="h-20 rounded bg-white" src="https://upload.wikimedia.org/wikipedia/commons/9/91/Octicons-mark-github.svg"/>
  <img class="h-20 rounded bg-white" src="https://avatars.githubusercontent.com/u/15658638?s=200&v=4"/>
  <img class="h-20 rounded bg-white" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b8/Fortran_logo.svg/1024px-Fortran_logo.svg.png"/>
  ...
</div>

</v-clicks>

</div>

---

# Instead it is about...

<div class="py-20">
<v-clicks>

- My personal journey and experience

- A collection of tools and tricks that I find the useful

- A chance for us to discuss about tools that many of us deal with everyday

</v-clicks>
</div>

---
layout: section
---

# Me in another multiverse

---

# First day of data analysis...

After spending 3 hours trying to figure out how to log on to the server...

<v-click>

```bash {1|2-5|6-}
user@server:~ $ cd data/
user@server:data $ ls
run-010.root    run-011.root    run-012.root    run-014.root
run-015.root    run-016.root    run-017.root    run-021.root
run-022.root    run-023.root    run-024.root    run-025.root
user@server:~ $ vim run-010.root
root  òþ   d	tÂÊ	tÂX   r      °   et§  § Ã)b¸ì}
¸##¾ï                                        ì    jo h   
 d    TFileF/home/user/data/run-009.root F/home/user/data/run-009.root  
jojoÄ   £   °   d    
tÁµ Ã)b¸ì}¸##¾ï              ì  ujo Q   
     P       dTBasketdet_A.xtree   }   è  ¹  nú ZL
+ u xµy¬UÅw£ÌµZ(R&Z¡P¦KÒ"C
àHÐhTpÆ8ÄÇh"¢1FÔõÇùÝ¬ó6çÜûê+ó}g¯µö>çÞ÷Z
3ýâwÌ¼|uÊ÷ìrÀï|ð÷2~`«ÜùE¯Z?tÃ!Ç^¿úáE
ÏH¦I8 ìÖQ.ädáZ°QXdÎ&²Ñ¨Æ½àø
Í×îèk7ðuz:&4$²£îÊ¬Ócjµ@Æ½Ñ³CK8¤­¨>Ny¯M`ú_nÀÚ¤eCOÈÞ}
 ÀxÂæíMÖÎeÜäÓåÜ6"1ùs»PýÆ97Ú0:fÔÂ8»@km#¬pxA½ì
YcÐ¼ÏVÐNBAÆ8;§³ðV]¸åÉ¼À×µ%âçF5w'¶ÀCàn
Ý9[ÛDô±úºa¹¯]Ø:â;LútZ3(Ú=½d Ê:ü°%áÏñm>
...
```

</v-click>

<v-click>
  <p class="absolute bottom-50 right-50 transform -rotate-340 text-6xl text-green-600">?</p>
</v-click>

---

# Looking at some existing codebase...

```bash {1|2-}
user@server:~ $ cd analysis/
user@server:analysis $ ls
build/                                  env.sh                     MappingModules_cxx_ACLiC_dict_rdict.pcm
CalibrateData.cxx                       etc/                       MappingModules_cxx.d
CalibrateData_cxx_ACLiC_dict_rdict.pcm  evt_files/                 MappingModules_cxx.so
CalibrateData_cxx.d                     ExtractHistograms.cxx      ReadInBadPixels.cxx
CalibrateData_cxx.so                    ExtractHistograms_cxx.so   ReadInBadPixels_cxx.so
calibrations/                           GeometryEfficiency.cxx     README.md
config/                                 GeometryEfficiency_cxx.so  rootlogon.C
ConvertEvt.cxx                          include/                   RunInfo.cxx
ConvertEvt_cxx.so                       lib/                       RunInfo_cxx.so
detectors/                              LICENSE                    slurm
DrawEnergySpectra.cxx                   log/                       src/
DrawGeometryEfficiency.cxx              Makefile                   tmp/
DrawHitPattern.cxx                      mappers/
electronics/                            MappingModules.cxx
```

<v-click>
  <p class="absolute bottom-50 right-50 transform -rotate-340 text-9xl text-green-600">?!</p>
</v-click>

---

# Quit grad school!

<v-click>

<div class="grid grid-cols-2 gap-x-10">

  On résumé

  Actual experience

  - Experienced in C/C++
  - Able to handle a mouse with either hand
  - Started using a mouse when there was still a ball underneath it

  ```cpp
  #include <iostream>

  int main() {
    std::cout << "Hello universe!" << std::endl;
    return 0;
  }
  ```
</div>

</v-click>


---
layout: section
---

# What if

---

# What if...

<v-clicks>

- there is an easier way to log on to the server?
- there is a way to navigate the server with a 🖱️? (not to let my talent go wasted)
- there is some simple app that can view the ROOT files?
- there is a language that does not require a compiler? (`Makefile`, `*.so`, `*.h`, ... 😮‍💨)
- I could find more useful discussions on Stack Overflow?
- I could open up any script and just run the functions?
- my text editor could help me to code?
- I could install any libraries or languages onto the server without administrator privilege, so that I don't have to reinvent the wheel?
- ...

</v-clicks>

---
layout: section
---

# Let's use a modern editor

---

# A modern editor

<v-click>

- Debatable among experts and hobbyists (Emacs, Vim, Sublime Text, Atom, Notepad++, ...)

</v-click>

<v-click>

- But for people who just want something simple yet powerful...

<br>

<div class="grid grid-cols-2 gap-x-10">

<div class="inline-block align-middle">
  <img class="h-20" src="https://media.githubusercontent.com/media/microsoft/vscode-docs/69aa119cd341268a1368980a4e40ab7c5a2964a4/images/logo-stable.png"/>

  ```
  > Visual Studio Code
  > a.k.a. VS Code
  > Cross-platform, open-source, and free
  ```
</div>

<div>
  <img class="rounded h-70" src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/vscode-rank.png?raw=true"/>
  <a class="text-xs" href="https://insights.stackoverflow.com/survey/2021#section-most-popular-technologies-integrated-development-environment" target="_blank">
    https://insights.stackoverflow.com/survey/2021
  </a>
</div>

</div>

</v-click>

---
layout: two-cols
---

# Log on to server

<v-click>

PuTTY

<div class="grid grid-cols-5 gap-x-0 gap-y-3 place-items-center">
  <img class="h-20" src="https://upload.wikimedia.org/wikipedia/commons/b/b6/PuTTY_icon_128px.png"/>
  <img class="h-40 rounded col-span-4" src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/putty-window.png?raw=true"/>

  <img class="h-45 rounded col-span-5" src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/putty-terminal.png?raw=true"/>
</div>

</v-click>

::right::
<v-click>

# VS Code

Extension: Remote SSH

<img class="h-60" src="https://github.com/microsoft/vscode-remote-release/blob/137075c759a068703a1dd55697e7d6137d96dcaf/docs/images/ssh-readme.gif?raw=true"/>

</v-click>

---

# User interface

<a class="text-xs" href="https://code.visualstudio.com/docs/getstarted/userinterface" target="_blank">
  https://code.visualstudio.com/docs/getstarted/userinterface
</a>

<div class="grid grid-cols-4">

<div class="col-span-3">
  <img class="h-90" src="https://media.githubusercontent.com/media/microsoft/vscode-docs/69aa119cd341268a1368980a4e40ab7c5a2964a4/docs/getstarted/images/userinterface/hero.png"/>
</div>

- Terminal
- Editor
- Explorer
- Status

</div>

---

# User interface - grid layout

<a class="text-xs" href="https://code.visualstudio.com/docs/getstarted/userinterface" target="_blank">
  https://code.visualstudio.com/docs/getstarted/userinterface
</a>

<img class="h-90" src="https://media.githubusercontent.com/media/microsoft/vscode-docs/69aa119cd341268a1368980a4e40ab7c5a2964a4/docs/getstarted/images/userinterface/grid-layout.gif"/>

---

# Extension Marketplace

<a class="text-xs" href="https://code.visualstudio.com/docs/editor/extension-marketplace" target="_blank">
  https://code.visualstudio.com/docs/editor/extension-marketplace
</a>

<div class="grid grid-cols-2 gap-x-1 place-items-center">

  <img class="h-60" src="https://media.githubusercontent.com/media/microsoft/vscode-docs/69aa119cd341268a1368980a4e40ab7c5a2964a4/docs/editor/images/extension-marketplace/extensions-view-filter-menu.png"/>

  <img class="h-60" src="https://media.githubusercontent.com/media/microsoft/vscode-docs/69aa119cd341268a1368980a4e40ab7c5a2964a4/docs/editor/images/extension-marketplace/uninstall-extension.png"/>

</div>

---

<iframe class="container h-100" src="https://marketplace.visualstudio.com/search?target=VSCode&category=Visualization&sortBy=Installs"></iframe>

---

# ROOT File Viewer

<a class="text-xs" href="https://root.cern/blog/vscode-extension-announcement/" target="_blank">
  https://root.cern/blog/vscode-extension-announcement/
</a>
<img class="h-90" src="https://github.com/AlbertoPdRF/root-file-viewer/blob/a5cb3645a8847d0a4e6735dc2378950ddd593b87/demo.gif?raw=true"/>

---
layout: section
---

# An easier language?


<v-click>

Python

</v-click>

---

# Sum from 1 to 10,000,000

<div class="grid grid-cols-4 gap-x-2">

<v-click>

With C++
<div class="col-span-3">

```cpp
#include <iostream>

int main() {
  int result = 0;
  for (int i = 1; i <= int(1e7); i++) {
    result += i;
  }
  std::cout << "Sum: " << result << std::endl;
}
```

</div>

</v-click>

<v-click>

With Python
<div class="col-span-3">

```python
result = 0
for i in range(1, int(1e7) + 1):
  result += i
print(f'Sum: {result}')
```

</div>

</v-click>

</div>

<v-click>

**Performance**

</v-click>

<v-clicks>

- C++: 28 ms
- Python: 883 ms

</v-clicks>

---

# So Python is just a *slow* language...?

<div class="grid grid-cols-2 gap-y-10">
<v-click>

- Previously: <span class="text-blue-800">28 ms</span> (C++), <span class="text-blue-400">883 ms</span> (Python)
```bash
user@server:~ $ g++ sum.cxx && time ./a.out  # C++
user@server:~ $ time python sum.py           # Python
```
</v-click>

<v-click>

- Include compilation time of C++: <span class="text-blue-800">439 ms</span>
```bash
user@server:~ $ time g++ sum.cxx && ./a.out
```
</v-click>

<v-click>

- Write efficient Pythonic code: <span class="text-blue-400">229 ms</span>
```python
result = sum(range(1, int(1e7) + 1))
print(f'Sum: {result}')
```
</v-click>

<v-click>

- Write a better algorithm: <span class="text-blue-400">45 ms</span>
```python
i_start, i_stop = 1, int(1e7)
result = (i_stop - i_start + 1) * (i_start + i_stop) / 2
print(f'Sum: {result}')
```
</v-click>

</div>


---

# What do we really want?

As a PhD student working on data analysis...

<div class="grid grid-cols-1 gap-y-10">
<v-clicks>

- **Runtime** is usually not the most important thing
- **Compile time** can be a big problem too
- IMO, **development time** is the most important thing
  * Learning time
  * Writing time
  * Testing time
  * Debug time
  * Documentation time
  * ...

</v-clicks>
</div>

---
layout: section
---

# Python + ROOT

---

# PyROOT - CERN

<a class="text-xs" href="https://root.cern/releases/release-62200/">
  https://root.cern/releases/release-62200/
</a>
<iframe class="container h-80" src="https://root.cern/releases/release-62200/#highlights"></iframe>

---

# Smoothest transition from C++ to Python

<div class="grid grid-cols-2 gap-x-5">

<v-click>

<div>

```cpp
void test() {
  TH1D* hist = new TH1D("hist", "Title", 100, -3, 3);
  hist->FillRandom("gaus", 10000);
  hist->Draw();
}
```

```bash
user@server:~ $ root test.cxx
root [0] 
Processing test.cpp...
Info in <TCanvas::MakeDefCanvas>:  created default TCan
vas with name c1
root [1] 
```

<img class="h-40 absolute bottom-5 border-1 border-blue-600" src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/root-demo-gaus-histogram.png?raw=true"/>

</div>

</v-click>

<v-click>

<div>

```python
from ROOT import TH1D
hist = TH1D('hist', 'Title', 100, -3, 3)
hist.FillRandom('gaus', 10000)
hist.Draw()
 
```

```bash
user@server:~ $ python -i test.py
Info in <TCanvas::MakeDefCanvas>:  created default TCan
vas with name c1
>>> 
```

<img class="h-40 absolute bottom-5 border-1 border-blue-300" src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/root-demo-gaus-histogram.png?raw=true"/>

</div>

</v-click>

</div>

---

# Writing C++ within Python

<div class="grid grid-cols-2 gap-x-5">

```python {all|1|3-11|3,9,11|13-14|16-|all}
import ROOT

cpp_code = """
double square(double x) { return x * x; }

class CxxObject {
public:
    CxxObject() { cout << "Constructor" << endl; }
    double tau() { return 2 * TMath::Pi(); }
};
"""

# inject the code into ROOT interpreter
ROOT.gInterpreter.ProcessLine(cpp_code)

# usage
ROOT.square(1.1)        # Output: 1.21
obj = ROOT.CxxObject()  # Print: Constructor
obj.tau()               # Output: 6.283185307179586
```

<div>

<v-after>

- C++ code is just-in-time compiled (jitted)

</v-after>

<v-click>

- If using for multiple times, compile it once:

```python
ROOT.gSystem.CompileMacro('test.cxx', 'fOck', 'myfunc')
```
</v-click>

<v-click>

- Then reuse as a *shared object* (`.so`):

```python
ROOT.gSystem.Load('./myfunc.so')
```
</v-click>

</div>

</div>

---

# Or deal only with ROOT I/O

<div class="grid grid-cols-2 gap-x-30">

```mermaid {scale: 0.9}
flowchart LR
  in_file([input.root])
  out_file([output.root])
  root_io(ROOT I/O)
  data_cleaning[Data cleaning]
  analysis[Analysis]
  visualization[Visualization]
  inference[Inference]

  in_file --- root_io
  out_file --- root_io
  subgraph python [Python libraries: numpy, matplotlib, etc.]
    root_io --> data_cleaning
    root_io --> analysis
    root_io --> visualization
    root_io --> inference
  end

  style in_file        fill: #f7f6a3, stroke: #000000, stroke-width: 1px
  style out_file       fill: #f7f6a3, stroke: #000000, stroke-width: 1px
  style root_io        fill: #94f7f7, stroke: #000000, stroke-width: 3px
  style data_cleaning  fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style analysis       fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style visualization  fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style inference      fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style python         fill: #fbe8fc, stroke: #0e6114, stroke-width: 3px
```

<div v-click>

Two primary options:
- `ROOT.RDataFrame` object's `AsNumpy()` function 😅
- `uproot` - a pure Python library ✅

<br>

<img class="h-20" src="https://github.com/scikit-hep/uproot4/blob/81624d71f0c1c7cefce2db78c069e9f98bea3f65/docs-img/logo/logo-600px.png?raw=true"/>

</div>

</div>


---

# Or deal only with ROOT I/O

```mermaid
flowchart LR
  in_file([input.root])
  out_file([output.root])
  root_io(uproot)
  data_cleaning[Data cleaning]
  analysis[Analysis]
  visualization[Visualization]
  inference[Inference]

  in_file --- root_io
  out_file --- root_io
  subgraph python [Python]
    root_io --> data_cleaning
    root_io --> analysis
    root_io --> visualization
    root_io --> inference
    data_cleaning -.- data_cleaning_lib[pandas, regex, ...]
    analysis -.- analysis_lib[numpy, scipy, sklearn, astropy, ...]
    visualization -.- visualization_lib[matplotlib, seaborn, plotly, ...]
    inference -.- inference_lib[statsmodels, tensorflow, pymc3, ...]
  end

  style in_file        fill: #f7f6a3, stroke: #000000, stroke-width: 1px
  style out_file       fill: #f7f6a3, stroke: #000000, stroke-width: 1px
  style root_io        fill: #94f7f7, stroke: #000000, stroke-width: 3px
  style data_cleaning  fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style analysis       fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style visualization  fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style inference      fill: #b0f5b5, stroke: #000000, stroke-width: 1px
  style python         fill: #fbe8fc, stroke: #0e6114, stroke-width: 3px
```

---
layout: section
---

# Ugh... too many libraries

---

# How to maintain all these libraries?

<br>
<v-click>

<img class="h-20" src="https://raw.githubusercontent.com/conda/conda/0b1312ce65bf0fbb8cbea3750f07c32a2492c57a/docs/source/img/conda_logo.svg"/>

</v-click>
<br>

<v-clicks>

- A package manager
- Cross-platform (Linux, Windows, MacOS)
- Originally developed for Python
- Can be used for other languages: C/C++, JavaScript, Fortran, Latex, etc.

</v-clicks>

<v-click>

Installing ROOT in one line (10 minutes ~ 4 hours):
```bash
user@server:~ $ conda install root
```
</v-click>

---
layout: two-cols
---

# Common usage

```bash {all|1|2|3|4|5|5-20|21|22-23|all}
user@server:~ $ mkdir project
user@server:~ $ cd project
user@server:project $ touch environment.yml
user@server:project $ # edit environment.yml
user@server:project $ conda env create --prefix ./test
Collecting package metadata (repodata.json): done
Solving environment: done

Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
#     $ conda activate /home/fanurs/project/test
#
# To deactivate an active environment, use
#
#     $ conda deactivate

user@server:project $ conda activate ./test
(test) user@server:project $ which conda
/home/fanurs/project/test/bin/conda
```

::right::

<v-after>

#### `environment.yml`

</v-after>

<div class="border-1 border-green-900">

```yaml {0|all|1|2-4|5-7|5,8-10|5,11-17|5,18-24|25-|all}
name: test
channels:
  - anaconda
  - conda-forge
dependencies:
  - conda-build
  - python=3.8
  # common scientific tools
  - numpy>=1.19.0
  - scikit-learn>=0.24.0
  # data structure and files I/O
  - pandas
  - uproot>=4.0.7
  - root=6.22.6
  # plotting
  - matplotlib>=3.3.0
  - plotly::plotly>=5.0.0
  # non-Python libraries
  - gxx_linux-64 # GNU C++ compiler: g++
  - boost-cpp # C++ on steroids
  - nlohmann_json=3.9.1 # C++ JSON library
  - gfortran_osx-64 # GNU Fortran compiler
  - miktex # TeX/LaTeX
  - nodejs # JavaScript runtime environment
variables:
  - PROJECT_DIR: "/home/fanurs/project/test/"
```

</div>


---
layout: section
---

# Ready to work!

Live demo

---
layout: section
---

# Advertisement

---
layout: full
---

<a href="https://github.com/" target="_blank">
  https://github.com/
</a>
<img class="absolute top-0 transform scale-75" src="https://github.com/Fanurs/myself/blob/main/slidev/projects/20210927-FRIBGO/github.png?raw=true"/>

---
layout: full
---

<a href="https://copilot.github.com/" target="_blank">
  https://copilot.github.com/
</a>
<iframe class="container h-100" src="https://copilot.github.com/"></iframe>

---
layout: full
---

<a href="https://sli.dev/" target="_blank">
  https://sli.dev/
</a>
<iframe class="container h-100" src="https://sli.dev/"></iframe>
