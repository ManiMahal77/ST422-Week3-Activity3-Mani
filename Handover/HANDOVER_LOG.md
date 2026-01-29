# HANDOVER_LOG.md

<!--- -------------------------------------------------------------------------
This is a template, so ensure you remove instructions, such as these comments
and all material not task-relevant before the final commit.
-------------------------------------------------------------------------- --->

## Handover log

Each entry is added by the handover recipient after attempting to reproduce the repo outputs using only the README.

Template (copy and fill in):

- Date: 29/01/2026
- Recipient: Calum Smith
- Repo tested (URL or repo name): https://github.com/ManiMahal77/ST422-Week3-Activity3-Mani.git
- OS: MacOS
- R version: 4.5.2
- RStudio version (optional): 2025.09.1+401 (2025.09.1+401)
- Step 1: renv::restore() (PASS/FAIL): FAIL
- Step 2: render report (PASS/FAIL): FAIL
- Command used to render: rmarkdown::render("reports/ST422 Week3 Activity 3.Rmd")
- Outputs created (list files that exist):
- If FAIL: error message (copy exact message):

Error: Error installing package 'data.table':
======================================

* installing *source* package ‘data.table’ ...
** this is package ‘data.table’ version ‘1.18.0’
** package ‘data.table’ successfully unpacked and MD5 sums checked
** using staged installation
*** pkg-config is not installed.
*** Compilation will now be attempted and if it works you can ignore this message. In
*** particular, this should be the case on Mac where zlib is built in or pkg-config
*** is not installed. However, if compilation fails, try 'locate zlib.h zconf.h' and
*** ensure the zlib development library is installed :
***   deb: zlib1g-dev (Debian, Ubuntu, ...)
***   rpm: zlib-devel (Fedora, EPEL, ...)
***   There is a zlib in brew for OSX but the built in zlib should work.
*** Note that zlib is required to compile R itself so you may find the advice in the R-admin
*** guide helpful regarding zlib. On Debian/Ubuntu, zlib1g-dev is a dependency of r-base as
*** shown by 'apt-cache showsrc r-base | grep ^Build-Depends | grep zlib', and therefore
*** 'sudo apt-get build-dep r-base' should be sufficient too.
*** To silence this message, please ensure that :
***   1) 'pkg-config --exists zlib' succeeds (i.e. $? -eq 0)
***   2) 'pkg-config --libs zlib' contains -lz
*** Compilation will now be attempted ...
* checking if R installation supports OpenMP with "-Xclang -fopenmp" ... no
* checking if R installation supports OpenMP with "-fopenmp" ... no
***
*** OpenMP not supported! data.table uses OpenMP to automatically
***   parallelize operations like sorting, grouping, file reading, etc.
*** For details on how to install the necessary toolchains on your OS see:
***   https://github.com/Rdatatable/data.table/wiki/Installation
*** Continuing installation without OpenMP support...
***
*** Compilation without compression support in fwrite
** libs
using C compiler: ‘Apple clang version 11.0.0 (clang-1100.0.33.12)’
using SDK: ‘MacOSX10.15.1.sdk’
clang -arch x86_64 -I"/Library/Frameworks/R.framework/Resources/include" -DNDEBUG   -I/opt/R/x86_64/include   -DNOZLIB -fPIC  -falign-functions=64 -Wall -g -O2  -c assign.c -o assign.o
In file included from assign.c:1:
In file included from ./data.table.h:25:
./po.h:2:10: fatal error: 'libintl.h' file not found
#include <libintl.h>
         ^~~~~~~~~~~
1 error generated.
make: *** [assign.o] Error 1
ERROR: compilation failed for package ‘data.table’
* removing ‘/Users/calumsmith/Documents/github/ST422-Week3-Activity3-Mani/renv/staging/1/data.table’
install of package 'data.table' failed [error code 1]

- One improvement suggestion for README/repo:

MacOS has different dependencies compared to Windows and so a suggestion would be to try and test for this before releasing if that is possible.
The "data.table" package is the main issue.
---

## Example entry (PASS)

- Date: 2026-01-25
- Recipient: Student B
- Repo tested: st422-week3-starter-repo
- OS: Windows 11
- R version: 4.3.2
- RStudio version (optional): 2023.12.1
- Step 1: renv::restore() (PASS/FAIL): PASS
- Step 2: render report (PASS/FAIL): PASS
- Command used to render: rmarkdown::render("reports/week3_report.Rmd")
- Outputs created (list files that exist):
  - outputs/tables/table1.csv
  - outputs/figures/churn_by_plan.png
  - outputs/figures/nps_by_churn.png
- If FAIL: error message (copy exact message): N/A
- One improvement suggestion for README/repo:
  - Add a short "Expected outputs" section with the file names and locations.

---

## Example entry (FAIL)

- Date: 2026-01-25
- Recipient: Student A
- Repo tested: st422-week3-example
- OS: macOS 15
- R version: 4.4.1
- RStudio version (optional): 2024.04.2
- Step 1: renv::restore() (PASS/FAIL): PASS
- Step 2: render report (PASS/FAIL): FAIL
- Command used to render: rmarkdown::render("reports/week3_report.Rmd")
- Outputs created (list files that exist):
  - outputs/tables/table1.csv
- If FAIL: error message (copy exact message):
  - Error: 'data/raw/st422_week3_subscription_v1.csv' does not exist in current working directory ('.../reports')
- One improvement suggestion for README/repo:
  - Add knitr root directory setting in the setup chunk so paths resolve from the repo root.