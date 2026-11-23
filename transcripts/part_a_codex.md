# Codex conversation

## User

y
Reproduce the target outcomes specified in
ps3/Group A/Choice 1/reproducibilityReport.Rmd,
using the materials in that folder.

Use ps3_check_template.qmd as the report template and
save the report as ps3_part_a.qmd.

Keep all analysis code visible and state which outcomes
you successfully reproduced. Leave the Checker's verdict
section blank for me to complete.

## Assistant

I’ll inspect the target report, the folder’s data and code, and the check template. Then I’ll run the analysis, record which outcomes match, and write `ps3_part_a.qmd` with the Checker’s verdict left blank.

## Activity

    $ rg --files -g 'AGENTS.md' -g 'ps3_check_template.qmd' -g 'reproducibilityReport.Rmd' -g '*' 'ps3/Group A/Choice 1' | head -80
    ps3/Group A/Choice 1/article.pdf
    ps3/Group A/Choice 1/reproducibilityReport.Rmd
    ps3/Group A/Choice 1/data/Empathy Gap Study 1 data.sav
    ps3/Group A/Choice 1/data/Empathy_Gap_Study_2_data.sav
    ✓ • 225ms

## Activity

    $ ls -la 'ps3/Group A/Choice 1' && find 'ps3/Group A/Choice 1' -maxdepth 2 -type f -print
    total 1408
    drwxr-xr-x  5 jayanthgorrepati  staff     160 Nov 22 22:12 .
    drwxr-xr-x  5 jayanthgorrepati  staff     160 Nov 22 22:12 ..
    -rw-r--r--  1 jayanthgorrepati  staff  713531 Nov 22 22:12 article.pdf
    drwxr-xr-x  4 jayanthgorrepati  staff     128 Nov 22 22:12 data
    -rw-r--r--  1 jayanthgorrepati  staff    3319 Nov 22 22:12 reproducibilityReport.Rmd
    ps3/Group A/Choice 1/data/Empathy_Gap_Study_2_data.sav
    ps3/Group A/Choice 1/data/Empathy Gap Study 1 data.sav
    ps3/Group A/Choice 1/reproducibilityReport.Rmd
    ps3/Group A/Choice 1/article.pdf
    ✓ • 0ms

## Activity

    $ sed -n '1,260p' 'ps3/Group A/Choice 1/reproducibilityReport.Rmd'
    ---
    title: "Reproducibility Report: Group A Choice 1"
    output:
      html_document:
        toc: true
        toc_float: true
    ---
    
    -------
    
    For this exercise, please try to reproduce the results from Study 1 of the associated paper (Joel, Teper, & MacDonald, 2014). The PDF of the paper is included in the same folder as this Rmd file.
    
    #### Methods summary:
    
    In study 1, 150 introductory psychology students were randomly assigned to a "real" or a "hypothetical" condition. In the real condition, participants believed that they would have a real opportuniy to connect with potential romantic partners. In the hypothetical condition, participants simply imagined that they are on a date. All participants were required to select their favorite profile and answer whether they were willing to exchange contact information.
    
    ------
    
    #### Target outcomes:
    
    Below is the specific result you will attempt to reproduce (quoted directly from the results section of Study 1):
    
    >> We next tested our primary hypothesis that participants would be more reluctant to reject the unattractive date when they believed the situation to be real rather than hypothetical. Only 10 of the 61 participants in the hypothetical condition chose to exchange contact information with the unattractive potential date (16%). In contrast, 26 of the 71 participants in the real condition chose to exchange contact information (37%). A chi-square test of independence indicated that participants were significantly less likely to reject the unattractive potential date in the real condition compared with the hypothetical condition, X^2(1, N = 132) = 6.77, p = .009.
    
    ------
    
    ```{r global_options, include=FALSE}
    knitr::opts_chunk$set(echo=TRUE, warning=FALSE, message=FALSE)
    ```
    
    # Step 1: Load packages
    
    ```{r}
    library(tidyverse) # for data munging
    library(knitr) # for kable table formating
    library(haven) # import and export 'SPSS', 'Stata' and 'SAS' Files
    library(readxl) # import excel files
    
    # #optional packages:
    # library(broom)
    # library(labelled)# converts SPSS's labelled to R's factor
    ```
    
    # Step 2: Load data
    
    ```{r}
    # Just Study 1
    d <- read_sav('data/Empathy Gap Study 1 data.sav')
    ```
    
    # Step 3: Tidy data
    
    ```{r}
    
    ```
    
    # Step 4: Run analysis
    
    ## Descriptive statistics
    
    > Only 10 of the 61 participants in the hypothetical condition chose to exchange contact information with the unattractive potential date (16%). In contrast, 26 of the 71 participants in the real condition chose to exchange contact information (37%).
    
    ```{r}
    # reproduce the above results here
    
    ```
    
    ## Inferential statistics
    
    > A chi-square test of independence indicated that participants were significantly less likely to reject the unattractive potential date in the real condition compared with the hypothetical condition, X^2(1, N = 132) = 6.77, p = .009.
    
    Hint: if you are using the function chisq.test(), make sure to set the continuity correction to false ("correct = FALSE") since sample size is greater than 20.
    
    ```{r}
    # reproduce the above results here
    
    ```
    
    # Step 5: Reflection
    
    Were you able to reproduce the results you attempted to reproduce? If not, what part(s) were you unable to reproduce?
    
    > ANSWER HERE
    
    How difficult was it to reproduce your results?
    
    > ANSWER HERE
    
    What aspects made it difficult? What aspects made it easy?
    
    > ANSWER HERE
    
    
    ✓ • 0ms

## Activity

    $ rg --files -g 'AGENTS.md' -g 'ps3_check_template.qmd' -g '*.qmd' -g '*.Rmd'
    ps2_inference.qmd
    ps3_check_template.qmd
    ps3_part_b.qmd
    ps3_part_a.qmd
    ps3/Group A/Choice 3/reproducibilityReport.Rmd
    ps3/Group A/Choice 2/reproducibilityReport.Rmd
    ps3/Group A/Choice 1/reproducibilityReport.Rmd
    ps3_reproducibility.qmd
    ps1_github.qmd
    ps3/Group B/Choice 3/reproducibilityReport.Rmd
    ps3/Group B/Choice 1/reproducibilityReport.Rmd
    ps3/Group B/Choice 2/reproducibilityReport.Rmd
    archive/meta-analysis_exercise.qmd
    archive/thomas_exercise_solutions.Rmd
    archive/blake_exercise.qmd
    archive/ps2.qmd
    archive/krefeld_schwalb_exercise_solutions.qmd
    archive/ggplot2_exercise.qmd
    archive/krefeld_schwalb_exercise.qmd
    archive/thomas_exercise.Rmd
    ✓ • 0ms

## Activity

    $ cat ps3_check_template.qmd
    ---
    title: "Reproducibility check: [Author et al. (Year)]"
    author: "[Your name]"
    date: today
    format:
      html:
        toc: true
    execute:
      echo: true
      warning: false
      message: false
    ---
    
    ## Article
    
    - Citation and DOI:
    - Data/materials repository URL:
    - Part A (known case) or Part B (a classmate's project paper):
    - Part B only: the classmate's project repo, and which target outcome is its key effect:
    
    ## Target outcomes
    
    Written **before** opening the data. Quote each from the paper. In Part B, one of these must
    be the project's key effect.
    
    | # | Target outcome (quoted) | Paper value(s) |
    |---|---|---|
    | 1 | | |
    | 2 | | |
    | 3 | | |
    
    ## Materials inventory
    
    | Item | Available? | Notes |
    |---|---|---|
    | Raw data | | |
    | Processed data | | |
    | Codebook / variable descriptions | | |
    | Analysis code | | |
    | Preregistration | | |
    
    ## Reproduction
    
    The agent's work, under your direction. Keep all code visible.
    
    ```{r}
    #| label: setup
    library(tidyverse)
    ```
    
    ```{r}
    #| label: load
    ```
    
    ```{r}
    #| label: preprocess
    ```
    
    ```{r}
    #| label: analysis
    ```
    
    ## Checker's verdict
    
    Filled in by you, not the agent.
    
    | # | Paper value | Reproduced value | Verdict (exact / minor / major / not reproducible) | Reason for discrepancy |
    |---|---|---|---|---|
    | 1 | | | | |
    | 2 | | | | |
    | 3 | | | | |
    
    Agent's own claim about success, and whether it was right:
    
    ## Time
    
    - Your time (hours):
    - Agent wall-clock time (hours):
    - Stopped at the 4-hour cap? What remained:
    
    ## Assessment
    
    Is the primary result analytically reproducible? What would have made this take 30 minutes?
    
    ## AI documentation
    
    - Agent and interface (e.g., Claude Code, Codex CLI, Cursor):
    - Model and version, if the tool reports it:
    - Context you gave it (files, instructions, any context file):
    - Number of times you intervened, and the most important intervention:
    - Transcript: link to the exported transcript in your repo (`transcripts/`). If your tool
      cannot export one, paste your prompts in order here instead.
    ✓ • 0ms

## Activity

    $ cat ps3_part_a.qmd
    ---
    title: "Reproducibility check: [Author et al. (Year)]"
    author: "[Your name]"
    date: today
    format:
      html:
        toc: true
    execute:
      echo: true
      warning: false
      message: false
    ---
    
    ## Article
    
    - Citation and DOI:
    - Data/materials repository URL:
    - Part A (known case) or Part B (a classmate's project paper):
    - Part B only: the classmate's project repo, and which target outcome is its key effect:
    
    ## Target outcomes
    
    Written **before** opening the data. Quote each from the paper. In Part B, one of these must
    be the project's key effect.
    
    | # | Target outcome (quoted) | Paper value(s) |
    |---|---|---|
    | 1 | | |
    | 2 | | |
    | 3 | | |
    
    ## Materials inventory
    
    | Item | Available? | Notes |
    |---|---|---|
    | Raw data | | |
    | Processed data | | |
    | Codebook / variable descriptions | | |
    | Analysis code | | |
    | Preregistration | | |
    
    ## Reproduction
    
    The agent's work, under your direction. Keep all code visible.
    
    ```{r}
    #| label: setup
    library(tidyverse)
    ```
    
    ```{r}
    #| label: load
    ```
    
    ```{r}
    #| label: preprocess
    ```
    
    ```{r}
    #| label: analysis
    ```
    
    ## Checker's verdict
    
    Filled in by you, not the agent.
    
    | # | Paper value | Reproduced value | Verdict (exact / minor / major / not reproducible) | Reason for discrepancy |
    |---|---|---|---|---|
    | 1 | | | | |
    | 2 | | | | |
    | 3 | | | | |
    
    Agent's own claim about success, and whether it was right:
    
    ## Time
    
    - Your time (hours):
    - Agent wall-clock time (hours):
    - Stopped at the 4-hour cap? What remained:
    
    ## Assessment
    
    Is the primary result analytically reproducible? What would have made this take 30 minutes?
    
    ## AI documentation
    
    - Agent and interface (e.g., Claude Code, Codex CLI, Cursor):
    - Model and version, if the tool reports it:
    - Context you gave it (files, instructions, any context file):
    - Number of times you intervened, and the most important intervention:
    - Transcript: link to the exported transcript in your repo (`transcripts/`). If your tool
      cannot export one, paste your prompts in order here instead.
    ✓ • 0ms

## Activity

    $ sed -n '1,220p' ps3_part_b.qmd
    ---
    title: "Reproducibility check: [Author et al. (Year)]"
    author: "[Your name]"
    date: today
    format:
      html:
        toc: true
    execute:
      echo: true
      warning: false
      message: false
    ---
    
    ## Article
    
    - Citation and DOI:
    - Data/materials repository URL:
    - Part A (known case) or Part B (a classmate's project paper):
    - Part B only: the classmate's project repo, and which target outcome is its key effect:
    
    ## Target outcomes
    
    Written **before** opening the data. Quote each from the paper. In Part B, one of these must
    be the project's key effect.
    
    | # | Target outcome (quoted) | Paper value(s) |
    |---|---|---|
    | 1 | | |
    | 2 | | |
    | 3 | | |
    
    ## Materials inventory
    
    | Item | Available? | Notes |
    |---|---|---|
    | Raw data | | |
    | Processed data | | |
    | Codebook / variable descriptions | | |
    | Analysis code | | |
    | Preregistration | | |
    
    ## Reproduction
    
    The agent's work, under your direction. Keep all code visible.
    
    ```{r}
    #| label: setup
    library(tidyverse)
    ```
    
    ```{r}
    #| label: load
    ```
    
    ```{r}
    #| label: preprocess
    ```
    
    ```{r}
    #| label: analysis
    ```
    
    ## Checker's verdict
    
    Filled in by you, not the agent.
    
    | # | Paper value | Reproduced value | Verdict (exact / minor / major / not reproducible) | Reason for discrepancy |
    |---|---|---|---|---|
    | 1 | | | | |
    | 2 | | | | |
    | 3 | | | | |
    
    Agent's own claim about success, and whether it was right:
    
    ## Time
    
    - Your time (hours):
    - Agent wall-clock time (hours):
    - Stopped at the 4-hour cap? What remained:
    
    ## Assessment
    
    Is the primary result analytically reproducible? What would have made this take 30 minutes?
    
    ## AI documentation
    
    - Agent and interface (e.g., Claude Code, Codex CLI, Cursor):
    - Model and version, if the tool reports it:
    - Context you gave it (files, instructions, any context file):
    - Number of times you intervened, and the most important intervention:
    - Transcript: link to the exported transcript in your repo (`transcripts/`). If your tool
      cannot export one, paste your prompts in order here instead.
    ✓ • 0ms

## Activity

    $ which Rscript; which quarto; which pdftotext; git status --short
    /usr/local/bin/Rscript
    /usr/local/bin/quarto
    pdftotext not found
    ?? ps3_part_a.qmd
    ?? ps3_part_b.qmd
    ✓ • 23ms

## Activity

    $ python3 -c 'import pypdf; r=pypdf.PdfReader("ps3/Group A/Choice 1/article.pdf"); print(len(r.pages)); print(r.pages[0].extract_text()[:5000])'
    Traceback (most recent call last):
      File "<string>", line 1, in <module>
        import pypdf; r=pypdf.PdfReader("ps3/Group A/Choice 1/article.pdf"); print(len(r.pages)); print(r.pages[0].extract_text()[:5000])
        ^^^^^^^^^^^^
    ModuleNotFoundError: No module named 'pypdf'
    ✗ (1) • 196ms

## Activity

    $ ls -la; ls -la ps3; ls -la 'ps3/Group A'; Rscript -e 'cat("haven:",requireNamespace("haven",quietly=TRUE),"\nknitr:",requireNamespace("knitr",quietly=TRUE),"\n")'
    total 80
    drwxr-xr-x  15 jayanthgorrepati  staff   480 Nov 22 22:13 .
    drwxr-x---+ 48 jayanthgorrepati  staff  1536 Nov 22 22:12 ..
    drwxr-xr-x  12 jayanthgorrepati  staff   384 Nov 22 22:12 .git
    -rw-r--r--   1 jayanthgorrepati  staff   127 Nov 22 22:12 .gitignore
    -rw-r--r--   1 jayanthgorrepati  staff   550 Nov 22 22:12 README.md
    drwxr-xr-x  12 jayanthgorrepati  staff   384 Nov 22 22:12 archive
    drwxr-xr-x   3 jayanthgorrepati  staff    96 Nov 22 22:12 in_class
    -rw-r--r--   1 jayanthgorrepati  staff  5132 Nov 22 22:12 ps1_github.qmd
    -rw-r--r--   1 jayanthgorrepati  staff  2238 Nov 22 22:12 ps2_inference.qmd
    drwxr-xr-x   4 jayanthgorrepati  staff   128 Nov 22 22:12 ps3
    -rw-r--r--   1 jayanthgorrepati  staff  1983 Nov 22 22:12 ps3_check_template.qmd
    -rw-r--r--   1 jayanthgorrepati  staff  1983 Nov 22 22:12 ps3_part_a.qmd
    -rw-r--r--   1 jayanthgorrepati  staff  1983 Nov 22 22:12 ps3_part_b.qmd
    -rw-r--r--   1 jayanthgorrepati  staff  5355 Nov 22 22:12 ps3_reproducibility.qmd
    drwxr-xr-x   2 jayanthgorrepati  staff    64 Nov 22 22:13 transcripts
    total 0
    drwxr-xr-x   4 jayanthgorrepati  staff  128 Nov 22 22:12 .
    drwxr-xr-x  15 jayanthgorrepati  staff  480 Nov 22 22:13 ..
    drwxr-xr-x   5 jayanthgorrepati  staff  160 Nov 22 22:12 Group A
    drwxr-xr-x   5 jayanthgorrepati  staff  160 Nov 22 22:12 Group B
    total 0
    drwxr-xr-x  5 jayanthgorrepati  staff  160 Nov 22 22:12 .
    drwxr-xr-x  4 jayanthgorrepati  staff  128 Nov 22 22:12 ..
    drwxr-xr-x  5 jayanthgorrepati  staff  160 Nov 22 22:12 Choice 1
    drwxr-xr-x  5 jayanthgorrepati  staff  160 Nov 22 22:12 Choice 2
    drwxr-xr-x  5 jayanthgorrepati  staff  160 Nov 22 22:12 Choice 3
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    haven: TRUE
    knitr: TRUE
    ✓ • 2.66s

## Assistant

The target passage gives two contact exchange counts and percentages, plus one chi-square test. I found the Study 1 SPSS file and a local article PDF. I’m checking the variable labels and exclusions before calculating those values.

## Activity

    $ rg -n 'Joel|Teper|MacDonald|doi|Study 1|contact' ps3_reproducibility.qmd README.md
    ps3_reproducibility.qmd:14:psychology found that a large fraction could not be reproduced without contacting the
    ps3_reproducibility.qmd:52:3. **Reproduce**, with an agent doing the work under your direction. Export the agent's
    ✓ • 0ms

## Activity

    $ python3 -c 'import importlib.util; print({x:bool(importlib.util.find_spec(x)) for x in ["fitz","pdfplumber","pypdfium2","PyPDF2"]})'
    {'fitz': False, 'pdfplumber': False, 'pypdfium2': False, 'PyPDF2': False}
    ✓ • 0ms

## Activity

    $ Rscript -e 'd <- haven::read_sav("ps3/Group A/Choice 1/data/Empathy Gap Study 1 data.sav"); cat("Rows:", nrow(d), " Columns:", ncol(d), "\n"); for (nm in names(d)) {x <- d[[nm]]; cat(nm, " | label=", attr(x,"label"), " | class=", class(x)[1], " | values=", paste(head(unique(x), 12), collapse=","), " | missing=", sum(is.na(x)), "\n", sep="")}'
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    Rows: 132  Columns: 125
    ID | label= | class=numeric | values=53,93,83,27,6,116,24,127,32,73,12,55 | missing=1
    attachment1 | label= | class=numeric | values=3,5,2,4,6,1,NA,7 | missing=3
    attachment2 | label= | class=numeric | values=4,1,6,7,5,2,3,NA | missing=3
    attachment3 | label= | class=numeric | values=5,3,6,2,4,1,7,NA | missing=3
    attachment4 | label= | class=numeric | values=3,4,6,2,5,7,NA,1 | missing=4
    attachment5 | label= | class=numeric | values=2,5,6,4,3,7,1,NA | missing=3
    attachment6 | label= | class=numeric | values=3,2,4,5,6,1,7,NA | missing=3
    attachment7 | label= | class=numeric | values=5,2,6,1,3,4,7,NA | missing=3
    attachment8 | label= | class=numeric | values=2,5,3,4,1,6,NA,7 | missing=3
    attachment9 | label= | class=numeric | values=4,5,3,2,7,6,1,NA | missing=3
    attachment10 | label= | class=numeric | values=3,2,6,4,1,5,7,NA | missing=3
    attachment11 | label= | class=numeric | values=5,3,6,4,7,1,2,NA | missing=3
    attachment12 | label= | class=numeric | values=5,3,6,4,7,2,NA | missing=3
    attachment13 | label= | class=numeric | values=5,3,2,1,6,4,7,NA | missing=4
    attachment14 | label= | class=numeric | values=2,3,4,5,1,6,7,NA | missing=3
    attachment15 | label= | class=numeric | values=4,3,5,2,6,7,1,NA | missing=1
    attachment16 | label= | class=numeric | values=3,2,6,NA,1,4,7,5 | missing=2
    attachment17 | label= | class=numeric | values=3,6,4,5,2,7,NA,1 | missing=1
    attachment18 | label= | class=numeric | values=2,3,5,NA,4,6,1,7 | missing=2
    attachment19 | label= | class=numeric | values=5,3,4,NA,2,6,1,7 | missing=2
    attachment20 | label= | class=numeric | values=3,2,4,1,5,6,NA,7 | missing=1
    attachment21 | label= | class=numeric | values=4,NA,3,6,2,5,1,7 | missing=6
    attachment22 | label= | class=numeric | values=3,NA,6,5,2,4,1 | missing=2
    attachment23 | label= | class=numeric | values=3,2,5,4,6,1,NA | missing=2
    attachment24 | label= | class=numeric | values=4,NA,3,5,6,7,2,1 | missing=5
    attachment25 | label= | class=numeric | values=3,NA,5,4,2,1,6 | missing=3
    attachment26 | label= | class=numeric | values=4,6,1,5,2,7,3,NA | missing=1
    attachment27 | label= | class=numeric | values=3,5,2,4,NA,1,6,7 | missing=4
    attachment28 | label= | class=numeric | values=5,4,3,2,6,NA,1,7 | missing=3
    attachment29 | label= | class=numeric | values=3,NA,2,5,6,4,1,7 | missing=3
    attachment30 | label= | class=numeric | values=5,3,6,7,1,4,2 | missing=0
    attachment31 | label= | class=numeric | values=3,NA,2,5,1,6,4 | missing=3
    attachment32 | label= | class=numeric | values=5,NA,3,6,2,1,4,7 | missing=2
    attachment33 | label= | class=numeric | values=2,7,5,3,1,6,4,NA | missing=1
    attachment34 | label= | class=numeric | values=2,NA,3,5,4,7,1,6 | missing=3
    attachment35 | label= | class=numeric | values=2,NA,5,4,3,6,7,1 | missing=2
    attachment36 | label= | class=numeric | values=5,3,2,NA,4,6,1,7 | missing=2
    FOBA1 | label= | class=numeric | values=2,1,5,4,3 | missing=0
    FOBA2 | label= | class=numeric | values=1,5,2,4,3 | missing=0
    FOBA3 | label= | class=numeric | values=1,5,3,4,2 | missing=0
    FOBA4 | label= | class=numeric | values=3,1,5,4,2 | missing=0
    FOBA5 | label= | class=numeric | values=1,4,5,3,2 | missing=0
    FOBA6 | label= | class=numeric | values=2,5,4,1,3 | missing=0
    empathy1 | label= | class=numeric | values=2,3,4,5,1 | missing=0
    empathy2 | label= | class=numeric | values=5,3,4,1,2 | missing=0
    empathy3 | label= | class=numeric | values=1,4,3,2,5,NA | missing=1
    empathy4 | label= | class=numeric | values=2,1,3,4,5 | missing=0
    empathy5 | label= | class=numeric | values=4,3,5,2,1,NA | missing=1
    empathy6 | label= | class=numeric | values=4,NA,5,3,2,1 | missing=2
    empathy7 | label= | class=numeric | values=4,5,2,1,3 | missing=0
    empathy8 | label= | class=numeric | values=4,NA,2,3,5,1 | missing=1
    empathy9 | label= | class=numeric | values=4,5,3,2 | missing=0
    empathy10 | label= | class=numeric | values=4,5,1,3,2 | missing=0
    empathy11 | label= | class=numeric | values=4,NA,5,2,3,1 | missing=1
    empathy12 | label= | class=numeric | values=3,2,1,4,NA,5 | missing=1
    empathy13 | label= | class=numeric | values=4,1,2,3,NA,5 | missing=1
    empathy14 | label= | class=numeric | values=3,1,2,4,5 | missing=0
    empathy15 | label= | class=numeric | values=1,4,2,3,5,3.5 | missing=0
    empathy16 | label= | class=numeric | values=4,5,2,3,1 | missing=0
    empathy17 | label= | class=numeric | values=4,NA,5,3,2,1 | missing=1
    empathy18 | label= | class=numeric | values=1,2,3,5,4 | missing=0
    empathy19 | label= | class=numeric | values=1,NA,2,3,4,5 | missing=1
    empathy20 | label= | class=numeric | values=1,NA,4,5,3,2 | missing=1
    empathy21 | label= | class=numeric | values=1,NA,3,4,5,2 | missing=1
    empathy22 | label= | class=numeric | values=5,NA,4,3,1,2 | missing=1
    empathy23 | label= | class=numeric | values=1,NA,4,5,2,3 | missing=1
    empathy24 | label= | class=numeric | values=2,NA,4,3,1 | missing=1
    empathy25 | label= | class=numeric | values=4,NA,3,5,2,1 | missing=1
    empathy26 | label= | class=numeric | values=4,3,5,1,2 | missing=0
    empathy27 | label= | class=numeric | values=3,NA,4,1,2,5 | missing=2
    empathy28 | label= | class=numeric | values=4,2,3,5,1 | missing=0
    age | label= | class=numeric | values=18,20,19,22,33,17,NA,21,23,27 | missing=3
    livedincanada | label= | class=numeric | values=3,4,1,2 | missing=0
    orientation | label= | class=numeric | values=1,0,NA,2,6,3 | missing=1
    inrel | label= | class=numeric | values=2 | missing=0
    longterm | label= | class=numeric | values=2,1,NA | missing=2
    dating | label= | class=numeric | values=1,2,NA,3 | missing=2
    shortterm | label= | class=numeric | values=1,2,NA,3 | missing=2
    intimate | label= | class=numeric | values=2,1,NA,3 | missing=2
    otheropen | label=other/open | class=numeric | values=2,1,NA | missing=2
    drink | label= | class=numeric | values=4,2,1,3 | missing=0
    children | label= | class=numeric | values=1,4,2,3,NA | missing=2
    responseq1 | label= | class=numeric | values=4,2,3,1,5 | missing=0
    responseq2 | label= | class=numeric | values=4,3,2,1,5 | missing=0
    responseq3 | label= | class=numeric | values=4,3,2,5,1 | missing=0
    responseq4 | label= | class=numeric | values=4,3,2,NA,5 | missing=1
    reasontrue1 | label=self | class=numeric | values=3,2,4,1,NA,7.5 | missing=4
    motives1 | label=self | class=numeric | values=3,2,1,4,NA,5 | missing=1
    reasontrue2 | label=other | class=numeric | values=4,5,1,3,NA,2 | missing=4
    motives2 | label=other | class=numeric | values=3,NA,4,1,5,2 | missing=2
    reasontrue3 | label=self | class=numeric | values=4,2,3,1,NA,5 | missing=5
    motives3 | label=self | class=numeric | values=4,NA,2,3,1,5 | missing=3
    reasontrue4 | label=other | class=numeric | values=4,2,5,1,NA,3 | missing=4
    motives4 | label=other | class=numeric | values=3,NA,4,1,5,2 | missing=2
    reasontrue5 | label=self | class=numeric | values=3,2,4,1,NA,5 | missing=4
    motives5 | label=self | class=numeric | values=3,NA,2,1,4,5 | missing=2
    reasontrue6 | label=other | class=numeric | values=3,2,5,1,4,NA | missing=4
    motives6 | label=other | class=numeric | values=3,NA,4,1,5,2 | missing=2
    reasontrue7 | label=self | class=numeric | values=4,2,1,3,NA | missing=4
    motives7 | label=self | class=numeric | values=3,NA,1,4,2,5 | missing=3
    reasontrue8 | label=other | class=numeric | values=4,2,5,1,3,NA | missing=4
    motives8 | label=other | class=numeric | values=4,NA,1,3,5,2 | missing=3
    suspicious | label= | class=numeric | values=NA,2,4 | missing=19
    selfattractive | label= | class=numeric | values=5,8,4,NA,7,9,3,6,2,7.5,6.5,1 | missing=29
    otherattractive | label= | class=numeric | values=6,5,4,NA,1,8,2,7,3,3.5,4.5,9 | missing=29
    EmpathyPTtot | label= | class=numeric | values=3.85714285714286,2,3.28571428571429,3.71428571428571,3.42857142857143,3.57142857142857,2.71428571428571,3.14285714285714,4.14285714285714,2.57142857142857,2.85714285714286,4 | missing=0
    EmpathyFStot | label= | class=numeric | values=2.85714285714286,3.16666666666667,4.14285714285714,4.42857142857143,4.28571428571429,3.85714285714286,4.57142857142857,3.42857142857143,2.28571428571429,3.71428571428571,4,4.71428571428571 | missing=0
    EmpathyECtot | label= | class=numeric | values=3.85714285714286,4.4,5,4,4.42857142857143,4.14285714285714,4.28571428571429,2.71428571428571,3.42857142857143,4.71428571428571,3.57142857142857,3.71428571428571 | missing=0
    EmpathyPDtot | label= | class=numeric | values=3.42857142857143,4.5,4.42857142857143,4,3.85714285714286,3.71428571428571,3.66666666666667,3.57142857142857,3.33333333333333,3.28571428571429,3.14285714285714,3 | missing=0
    fobstot | label= | class=numeric | values=1.66666666666667,2.16666666666667,5,3,3.83333333333333,2.66666666666667,2.83333333333333,1.16666666666667,4.16666666666667,4,3.5,2 | missing=0
    attachmentavoidance | label= | class=numeric | values=3.55555555555556,3.85714285714286,4.33333333333333,4,4.94444444444444,3.66666666666667,2.22222222222222,2.66666666666667,3.30769230769231,4.22222222222222,5.61111111111111,3.61111111111111 | missing=1
    attachmentanxiety | label= | class=numeric | values=3.61111111111111,2.92307692307692,3.94444444444444,3,4.55555555555556,3.22222222222222,4.11111111111111,4.88888888888889,4.29411764705882,3.77777777777778,3.11111111111111,3.72222222222222 | missing=0
    stateguilttot | label= | class=numeric | values=3.75,2,4.5,1,4,5,1.25,3.25,3.5,4.25,2.75,3 | missing=0
    stateempathytot | label= | class=numeric | values=3.25,3,4.5,1,4,4.25,5,2,2.5,3.75,3.5,1.75 | missing=0
    excitementtot | label= | class=numeric | values=3.75,2,2.5,1.5,4,2.25,1,1.25,3,1.75,2.75,2.66666666666667 | missing=0
    compatibilitytot | label= | class=numeric | values=3,2.66666666666667,2,2.5,1,2.75,3.25,2.25,4,2.33333333333333,1.5,5.125 | missing=0
    very_otherfocused | label=four other-focused items that are strongly about the other | class=numeric | values=3.25,3,4.5,1,4,4.25,5,2,2.5,3.75,3.5,1.75 | missing=0
    less_otherfocused | label=four other-focused items that are more about own affect | class=numeric | values=3.75,2,4.5,1,4,5,1.25,3.25,3.5,4.25,2.75,3 | missing=0
    gender | label=01 | class=haven_labelled | values=1,0,NA | missing=3
    genderXcondition | label= | class=numeric | values=1,0,NA | missing=1
    REQUIRED_VARIABLES_START_BELOW | label=See below for variables required for analyses in paper | class=numeric | values=NA | missing=132
    condition | label=Independent variable - hypothetical vs. real condition | class=haven_labelled | values=1,0 | missing=0
    exchangeinfo | label=Key DV- whether or not participant agreed to exchange contact info | class=haven_labelled | values=1,2 | missing=0
    otherfocused_motives | label=eight other-focused items | class=numeric | values=3.5,2.5,4.5,1,4,4.125,2.125,5,1.625,2.875,4.375,4.25 | missing=0
    selffocused_motives | label=eight self-focused items | class=numeric | values=3.375,2.4,2.75,1.75,3.5,2.625,2,2.375,1.125,3,2.875,3.66666666666667 | missing=0
    ✓ • 439ms

## Activity

    $ sed -n '1,160p' ps3_reproducibility.qmd
    ---
    title: "Psych 251 PS3: Reproducibility check"
    format:
      html:
        toc: true
    ---
    
    **Due Sunday November 22, 11:59pm. Submit the URLs of your two rendered reports on Canvas.**
    
    ## Why
    
    Analytic reproducibility is the floor: given the authors' data and their description of the
    analysis, can someone else get the numbers in the paper? Past checks of open-data papers in
    psychology found that a large fraction could not be reproduced without contacting the
    authors, and that the process takes hours per paper. Agents change the cost of this work
    dramatically. This problem set asks how much. It also checks the original papers behind the
    class's own replication projects, and those results feed the class metascience project.
    
    Read Experimentology Chapter 3 (replication and reproducibility) and Chapter 13 (project
    management) first.
    
    ## Part A: calibration on a known case (about one hour)
    
    Pick **one** article from `ps3/Group A` or `ps3/Group B` (any Choice). Each folder has the
    PDF, the authors' data, and `reproducibilityReport.Rmd` describing the target outcomes.
    
    Direct an agent to reproduce the target outcomes. Give it the folder and the report template
    and nothing else. Do not help it beyond answering questions about where files are. When it
    declares itself done, render its report and fill in the **checker's verdict** section of
    `ps3_check_template.qmd` yourself: for each target statistic, did the agent's value match the
    paper (exact / minor discrepancy / major discrepancy / not attempted), and did the agent's
    own claim about success match reality?
    
    We know how each of these six articles turns out. The point of Part A is to see how your
    agent behaves when you can check it. Do just one article, then move on to Part B.
    
    ## Part B: a paper in the wild (the real work)
    
    You will be assigned the original paper behind a classmate's replication project. We assign
    only papers whose authors posted their data, never your own project's paper, and each paper
    goes to two students. Work independently: do not compare notes with the other checker, or
    with the student whose project it is, before the deadline.
    
    Using `ps3_check_template.qmd`:
    
    1. **Identify the target outcomes**: the key statistical results from the abstract and the
       primary analysis (typically 3–6 numbers: test statistics, p-values, effect sizes,
       descriptives). One of them must be the **key effect** of the classmate's replication
       project (we will tell you which result it is). Write them down before touching the data.
    2. **Obtain the data and materials** from the repository linked in the paper. Record what
       was available (data, codebook, analysis code) and what was missing.
    3. **Reproduce**, with an agent doing the work under your direction. Export the agent's
       transcript (see below). You may intervene as much as you like, but log it.
    4. **Report** per target outcome: reproduced value, paper value, verdict (exact / minor /
       major / not reproducible), and the reason for any discrepancy if you found one. Give the
       reproduced values as numbers, not just verdicts.
    5. **Time**: total hours, split into your time and agent wall-clock time. Stop at **4 hours**
       and report what remained.
    6. **Assessment**: is the paper's primary result analytically reproducible? What would the
       authors have needed to provide for this to take 30 minutes?
    
    ## Documenting the agent
    
    Both reports end with an **AI documentation** section: which agent and interface you used,
    the model and version if the tool reports it, what context you gave it, how often you
    intervened, and a link to the **exported transcript**, committed to your repo under
    `transcripts/`. If your tool cannot export a transcript, paste your prompts in order
    instead. Read the transcript before you commit it and remove anything private (tokens,
    file paths you would rather not share).
    
    We will analyze the transcripts in aggregate as part of the class report: which agents
    were used, where they went wrong, and how much human steering a reproduction takes. If
    you would prefer that yours not be included, say so in your report; it will not affect
    your grade.
    
    ## What you turn in
    
    Two rendered reports from `ps3_check_template.qmd` (one for Part A, one for Part B), each
    including the agent's code, your verdicts, and the AI documentation section. Put both in a public GitHub repo (with the transcripts), publish each one to [Posit Connect Cloud](https://connect.posit.cloud) (free account) with `quarto publish posit-connect-cloud <file>.qmd`, run in a terminal in your repository. This needs Quarto 1.9 or newer; check with `quarto --version`. Submit the two links.
    
    ## Grading (15 points)
    
    | | Points |
    |---|---|
    | Part A: verdict table complete and accurate against the known outcome | 4 |
    | Part B: target outcomes identified up front; data and materials inventory | 3 |
    | Part B: reproduction attempted for every target outcome with a per-outcome verdict and reasons | 5 |
    | Part B: time accounting, assessment, and AI documentation with transcript | 3 |
    
    Discrepancies are not your fault and cost no points; unexplained discrepancies do. The
    class's Part B verdicts will be aggregated (with agreement between the two checkers per
    paper) into a short report we will discuss together, and the key-effect results become the
    reproducibility measure in the class metascience project.
    ✓ • 0ms

## Activity

    $ mdls -name kMDItemTitle -name kMDItemAuthors -name kMDItemTextContent 'ps3/Group A/Choice 1/article.pdf' | head -40
    ps3/Group A/Choice 1/article.pdf: could not find ps3/Group A/Choice 1/article.pdf.
    ✓ • 0ms

## Activity

    $ Rscript -e 'cat(requireNamespace("pdftools",quietly=TRUE),"\n")'
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    FALSE
    ✓ • 57ms

## Activity

    $ Rscript -e 'd <- haven::read_sav("ps3/Group A/Choice 1/data/Empathy Gap Study 1 data.sav"); print(attributes(d$condition)); print(attributes(d$exchangeinfo)); print(table(d$condition,d$exchangeinfo,useNA="ifany")); print(chisq.test(table(d$condition,d$exchangeinfo),correct=FALSE))'
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    $label
    [1] "Independent variable - hypothetical vs. real condition"
    
    $format.spss
    [1] "F8.2"
    
    $class
    [1] "haven_labelled" "vctrs_vctr"     "double"
    
    $labels
    hypothetical         real
               0            1
    
    $label
    [1] "Key DV- whether or not participant agreed to exchange contact info"
    
    $format.spss
    [1] "F11.0"
    
    $display_width
    [1] 11
    
    $class
    [1] "haven_labelled" "vctrs_vctr"     "double"
    
    $labels
    yes  no
      1   2
    
    
         1  2
      0 10 51
      1 26 45
    
        Pearson's Chi-squared test
    
    data:  table(d$condition, d$exchangeinfo)
    X-squared = 6.7674, df = 1, p-value = 0.009284
    
    ✓ • 401ms

## Activity

    $ mdls -name kMDItemTitle -name kMDItemAuthors '/Users/jayanthgorrepati/problem_sets/ps3/Group A/Choice 1/article.pdf'
    /Users/jayanthgorrepati/problem_sets/ps3/Group A/Choice 1/article.pdf: could not find /Users/jayanthgorrepati/problem_sets/ps3/Group A/Choice 1/article.pdf.
    ✗ (1) • 0ms

## Activity

    $ Rscript -e 'd <- haven::read_sav("ps3/Group A/Choice 1/data/Empathy Gap Study 1 data.sav"); t <- table(d$condition,d$exchangeinfo); print(t); print(round(100*t[,1]/rowSums(t),3)); x<-chisq.test(t,correct=FALSE); cat(unname(x$statistic), unname(x$parameter), x$p.value, sum(t),"\n")'
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    
         1  2
      0 10 51
      1 26 45
         0      1
    16.393 36.620
    6.767375 1 0.00928393 132
    ✓ • 346ms

## Activity

    $ which pdfinfo; which mutool; which gs; which swift; strings 'ps3/Group A/Choice 1/article.pdf' | rg -i -m 12 'doi|joel|teper|macdonald|title|author|empathy'
    pdfinfo not found
    mutool not found
    gs not found
    /usr/bin/swift
                      <xmpGImg:image>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&#xA;p5j1m/vfV/8A7ad/6TSUr1m/vfV//tp3/pNJSvWb+99X/wDtp3/pNJSvWb+99X/+2nf+k0lK9Zv7&#xA;31f/AO2nf+k0lK9Zv731f/7ad/6TSUr1m/vfV/8A7ad/6TSUr1m/vfV//tp3/pNJSvWb+99X/wDt&#xA;p3/pNJTp/V6xruogA9JPsd/QWFtvbuWN08UlPUJKQu/pdX/F2f8AVVJKVh/0Sj/i2f8AUhJTO0lt&#xA;T3AhpDSQ48CByUlPK/tzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139yS&#xA;lftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA1&#xA;39ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySmVfW+oOe0Hq/TiCQIDXSfhokp1/rCWDp&#xA;/vfjVj1G+7MZ6lff82Dqkp5mcf8A7k9E/wDYcf8AkElKnH/7k9E/9hx/5BJSpx/+5PRP/Ycf+QSU&#xA;qcf/ALk9E/8AYcf+QSUqcf8A7k9E/wDYcf8AkElKnH/7k9E/9hx/5BJSpx/+5PRP/Ycf+QSUqcf/&#xA;ALk9E/8AYcf+QSUqcf8A7k9E/wDYcf8AkElOn9XzV+0Rsu6bYdjvbh0hln+dtGiSnp0lIXf0ur/i&#xA;7P8AqqklKw/6JR/xbP8AqQkpKQCCCJB0IKSmv+zenf8AcWn/ALbb/ckpX7N6d/3Fp/7bb/ckpX7N&#xA;6d/3Fp/7bb/ckpX7N6d/3Fp/7bb/AHJKV+zenf8AcWn/ALbb/ckpX7N6d/3Fp/7bb/ckpX7N6d/3&#xA;Fp/7bb/ckpX7N6d/3Fp/7bb/AHJKV+zenf8AcWn/ALbb/ckpQ6d08GRi0gj/AINv9ySk1tNN7dl7&#xA;G2NmdrwHCfgUlIf2b07/ALi0/wDbbf7klK/ZvTv+4tP/AG23+5JSv2b07/uLT/223+5JSv2b07/u&#xA;LT/223+5JSv2b07/ALi0/wDbbf7klK/ZvTv+4tP/AG23+5JSv2b07/uLT/223+5JSv2b07/uLT/2&#xA;23+5JSv2b07/ALi0/wDbbf7klM6sPEofvporrdxuYxrT94CSkySkLv6XV/xdn/VVJKVh/wBEo/4t&#xA;n/UhJSZJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklIXf0ur/i7&#xA;P+qqSUhw8zEGJQDfX/Ns/Pb+6PNJSb7Zif6ev/Pb/ekpX2zE/wBPX/nt/vSUr7Zif6ev/Pb/AHpK&#xA;V9sxP9PX/nt/vSUr7Zif6ev/AD2/3pKV9sxP9PX/AJ7f70lK+2Yn+nr/AM9v96SlfbMT/T1/57f7&#xA;0lK+2Yn+nr/z2/3pKV9sxP8AT1/57f70lK+2Yn+nr/z2/wB6SlfbMT/T1/57f70lK+2Yn+nr/wA9&#xA;v96SlfbMT/T1/wCe3+9JSvtmJ/p6/wDPb/ekpX2zE/09f+e3+9JSvtmJ/p6/89v96SlfbMT/AE9f&#xA;+e3+9JSvtmJ/p6/89v8AekpX2zE/09f+e3+9JSvtmJ/p6/8APb/ekpX2zE/09f8Ant/vSUr7Zif6&#xA;ev8Az2/3pKQuzMT7XWfXr/m7Pz2/vVeaSn//2Q==</xmpGImg:image>
             <dc:title>
             </dc:title>
             <dc:title>
             </dc:title>
             <dc:title>
             </dc:title>
                      <xapGImg:image>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&#xA;p5j1m/vfV/8A7ad/6TSUr1m/vfV//tp3/pNJSvWb+99X/wDtp3/pNJSvWb+99X/+2nf+k0lK9Zv7&#xA;31f/AO2nf+k0lK9Zv731f/7ad/6TSUr1m/vfV/8A7ad/6TSUr1m/vfV//tp3/pNJSvWb+99X/wDt&#xA;p3/pNJTp/V6xruogA9JPsd/QWFtvbuWN08UlPUJKQu/pdX/F2f8AVVJKVh/0Sj/i2f8AUhJTO0lt&#xA;T3AhpDSQ48CByUlPK/tzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139yS&#xA;lftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA1&#xA;39ySlftzqP8A5cdN/wA139ySlftzqP8A5cdN/wA139ySmVfW+oOe0Hq/TiCQIDXSfhokp1/rCWDp&#xA;/vfjVj1G+7MZ6lff82Dqkp5mcf8A7k9E/wDYcf8AkElKnH/7k9E/9hx/5BJSpx/+5PRP/Ycf+QSU&#xA;qcf/ALk9E/8AYcf+QSUqcf8A7k9E/wDYcf8AkElKnH/7k9E/9hx/5BJSpx/+5PRP/Ycf+QSUqcf/&#xA;ALk9E/8AYcf+QSUqcf8A7k9E/wDYcf8AkElOn9XzV+0Rsu6bYdjvbh0hln+dtGiSnp0lIXf0ur/i&#xA;7P8AqqklKw/6JR/xbP8AqQkpKQCCCJB0IKSmv+zenf8AcWn/ALbb/ckpX7N6d/3Fp/7bb/ckpX7N&#xA;6d/3Fp/7bb/ckpX7N6d/3Fp/7bb/AHJKV+zenf8AcWn/ALbb/ckpX7N6d/3Fp/7bb/ckpX7N6d/3&#xA;Fp/7bb/ckpX7N6d/3Fp/7bb/AHJKV+zenf8AcWn/ALbb/ckpQ6d08GRi0gj/AINv9ySk1tNN7dl7&#xA;G2NmdrwHCfgUlIf2b07/ALi0/wDbbf7klK/ZvTv+4tP/AG23+5JSv2b07/uLT/223+5JSv2b07/u&#xA;LT/223+5JSv2b07/ALi0/wDbbf7klK/ZvTv+4tP/AG23+5JSv2b07/uLT/223+5JSv2b07/uLT/2&#xA;23+5JSv2b07/ALi0/wDbbf7klM6sPEofvporrdxuYxrT94CSkySkLv6XV/xdn/VVJKVh/wBEo/4t&#xA;n/UhJSZJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklKSUpJSklIXf0ur/i7&#xA;P+qqSUhw8zEGJQDfX/Ns/Pb+6PNJSb7Zif6ev/Pb/ekpX2zE/wBPX/nt/vSUr7Zif6ev/Pb/AHpK&#xA;V9sxP9PX/nt/vSUr7Zif6ev/AD2/3pKV9sxP9PX/AJ7f70lK+2Yn+nr/AM9v96SlfbMT/T1/57f7&#xA;0lK+2Yn+nr/z2/3pKV9sxP8AT1/57f70lK+2Yn+nr/z2/wB6SlfbMT/T1/57f70lK+2Yn+nr/wA9&#xA;v96SlfbMT/T1/wCe3+9JSvtmJ/p6/wDPb/ekpX2zE/09f+e3+9JSvtmJ/p6/89v96SlfbMT/AE9f&#xA;+e3+9JSvtmJ/p6/89v8AekpX2zE/09f+e3+9JSvtmJ/p6/8APb/ekpX2zE/09f8Ant/vSUr7Zif6&#xA;ev8Az2/3pKQuzMT7XWfXr/m7Pz2/vVeaSn//2Q==</xapGImg:image>
    ✓ • 1.27s

## Activity

    $ strings 'ps3/Group A/Choice 1/article.pdf' | rg --max-columns 180 --max-columns-preview -i -m 15 '^/Title|^/Author|doi.org|10\.[0-9]{4}'
                               <xmpG:black>10.000002</xmpG:black>
                               <xmpG:magenta>10.000002</xmpG:magenta>
                               <xmpG:black>10.000002</xmpG:black>
                               <xmpG:magenta>10.000002</xmpG:magenta>
                               <xmpG:black>10.000002</xmpG:black>
                               <xmpG:cyan>10.000002</xmpG:cyan>
                               <xmpG:black>10.000002</xmpG:black>
                               <xmpG:magenta>10.000002</xmpG:magenta>
                               <xmpG:magenta>10.000002</xmpG:magenta>
                               <xmpG:black>10.000002</xmpG:black>
                               <xmpG:magenta>10.000002</xmpG:magenta>
                               <xmpG:black>10.000002</xmpG:black>
                               <xmpG:magenta>10.000002</xmpG:magenta>
                               <xmpG:black>10.000002</xmpG:black>
                               <xmpG:cyan>10.000002</xmpG:cyan>
    ✓ • 0ms

## Activity

    $ swift -e 'import Foundation; import PDFKit; let u = URL(fileURLWithPath: "ps3/Group A/Choice 1/article.pdf"); let d = PDFDocument(url: u)!; print("pages", d.pageCount); print(String((d.page(at: 0)?.string ?? "").prefix(3500)))'
    <unknown>:0: warning: option '-e' is only supported in swift-driver
    error: failed to create REPL target: '/Library/Developer/CommandLineTools/Library/PrivateFrameworks/LLDB.framework/Resources/repl_swift' doesn't contain the architecture i386
    ✓ • 7.32s

## Activity

    Searched the web for Joel Teper MacDonald 2014 empathy gap romantic rejection unattractive date 10 61 26 71 DOI

## Assistant

The SPSS labels identify `condition` as hypothetical (0) or real (1), and `exchangeinfo` as yes (1) or no (2). The cross-tab gives 10/61 and 26/71; Pearson’s chi-square without the continuity correction is 6.7674 with p = 0.009284. These round to every value in the target passage.

## Activity

    file changes: Completed · 1 changes
    Delete: /Users/jayanthgorrepati/problem_sets/ps3_part_a.qmd
    ---
    title: "Reproducibility check: [Author et al. (Year)]"
    author: "[Your name]"
    date: today
    format:
      html:
        toc: true
    execute:
      echo: true
      warning: false
      message: false
    ---
    
    ## Article
    
    - Citation and DOI:
    - Data/materials repository URL:
    - Part A (known case) or Part B (a classmate's project paper):
    - Part B only: the classmate's project repo, and which target outcome is its key effect:
    
    ## Target outcomes
    
    Written **before** opening the data. Quote each from the paper. In Part B, one of these must
    be the project's key effect.
    
    | # | Target outcome (quoted) | Paper value(s) |
    |---|---|---|
    | 1 | | |
    | 2 | | |
    | 3 | | |
    
    ## Materials inventory
    
    | Item | Available? | Notes |
    |---|---|---|
    | Raw data | | |
    | Processed data | | |
    | Codebook / variable descriptions | | |
    | Analysis code | | |
    | Preregistration | | |
    
    ## Reproduction
    
    The agent's work, under your direction. Keep all code visible.
    
    ```{r}
    #| label: setup
    library(tidyverse)
    ```
    
    ```{r}
    #| label: load
    ```
    
    ```{r}
    #| label: preprocess
    ```
    
    ```{r}
    #| label: analysis
    ```
    
    ## Checker's verdict
    
    Filled in by you, not the agent.
    
    | # | Paper value | Reproduced value | Verdict (exact / minor / major / not reproducible) | Reason for discrepancy |
    |---|---|---|---|---|
    | 1 | | | | |
    | 2 | | | | |
    | 3 | | | | |
    
    Agent's own claim about success, and whether it was right:
    
    ## Time
    
    - Your time (hours):
    - Agent wall-clock time (hours):
    - Stopped at the 4-hour cap? What remained:
    
    ## Assessment
    
    Is the primary result analytically reproducible? What would have made this take 30 minutes?
    
    ## AI documentation
    
    - Agent and interface (e.g., Claude Code, Codex CLI, Cursor):
    - Model and version, if the tool reports it:
    - Context you gave it (files, instructions, any context file):
    - Number of times you intervened, and the most important intervention:
    - Transcript: link to the exported transcript in your repo (`transcripts/`). If your tool
      cannot export one, paste your prompts in order here instead.

## Activity

    file changes: Completed · 1 changes
    Add: /Users/jayanthgorrepati/problem_sets/ps3_part_a.qmd
    ---
    title: "Reproducibility check: Joel et al. (2014), Study 1"
    author: "[Your name]"
    date: today
    format:
      html:
        toc: true
    execute:
      echo: true
      warning: false
      message: false
    ---
    
    ## Article
    
    - Citation and DOI: Joel, S., Teper, R., & MacDonald, G. (2014). “People Overestimate Their Willingness to Reject Potential Romantic Partners by Overlooking Their Concern for Other People.” *Psychological Science, 25*(12). [https://doi.org/10.1177/0956797614552828](https://doi.org/10.1177/0956797614552828).
    - Data/materials repository URL: None supplied in the Choice 1 folder. The local materials used here are `ps3/Group A/Choice 1/article.pdf`, `reproducibilityReport.Rmd`, and `data/Empathy Gap Study 1 data.sav`.
    - Part A (known case) or Part B (a classmate's project paper): **Part A, Group A, Choice 1, Study 1.**
    - Part B only: Not applicable.
    
    ## Target outcomes
    
    The targets below were specified in `ps3/Group A/Choice 1/reproducibilityReport.Rmd` before the data were inspected. They are quoted there from the article's Study 1 results.
    
    | # | Target outcome (quoted) | Paper value(s) |
    |---|---|---|
    | 1 | “Only 10 of the 61 participants in the hypothetical condition chose to exchange contact information with the unattractive potential date (16%).” | 10/61; 16% |
    | 2 | “In contrast, 26 of the 71 participants in the real condition chose to exchange contact information (37%).” | 26/71; 37% |
    | 3 | “A chi-square test of independence indicated that participants were significantly less likely to reject the unattractive potential date in the real condition compared with the hypothetical condition, X^2(1, N = 132) = 6.77, p = .009.” | χ²(1, N = 132) = 6.77; p = .009 |
    
    ## Materials inventory
    
    | Item | Available? | Notes |
    |---|---|---|
    | Raw data | No separate unprocessed file | The folder contains an author-provided Study 1 SPSS analysis dataset with 132 rows. The report describes 150 recruited students, but the supplied file does not contain the other 18 rows. |
    | Processed data | Yes | `data/Empathy Gap Study 1 data.sav`; Study 2 data are also present but not used. |
    | Codebook / variable descriptions | Partial | SPSS variable and value labels identify `condition` and `exchangeinfo`; no separate codebook is supplied. |
    | Analysis code | Partial | `reproducibilityReport.Rmd` gives the load command and specifies `chisq.test(..., correct = FALSE)`, but leaves the analysis chunks empty. |
    | Preregistration | Not supplied | No preregistration file is in the folder. |
    
    ## Reproduction
    
    All analysis code is shown below. The SPSS value labels establish the coding: `condition` is 0 = hypothetical and 1 = real; `exchangeinfo` is 1 = yes and 2 = no. The analysis uses the 132 rows in the supplied Study 1 dataset, with no additional exclusions.
    
    ```{r}
    #| label: setup
    library(haven)
    library(knitr)
    ```
    
    ```{r}
    #| label: load
    study1 <- read_sav("ps3/Group A/Choice 1/data/Empathy Gap Study 1 data.sav")
    
    # Display the source labels so the recoding is auditable.
    attr(study1$condition, "labels")
    attr(study1$exchangeinfo, "labels")
    ```
    
    ```{r}
    #| label: preprocess
    stopifnot(
      identical(unname(attr(study1$condition, "labels")), c(0, 1)),
      identical(names(attr(study1$condition, "labels")), c("hypothetical", "real")),
      identical(unname(attr(study1$exchangeinfo, "labels")), c(1, 2)),
      identical(names(attr(study1$exchangeinfo, "labels")), c("yes", "no"))
    )
    
    analysis_data <- data.frame(
      condition = factor(as.numeric(study1$condition),
                         levels = c(0, 1), labels = c("Hypothetical", "Real")),
      exchange = factor(as.numeric(study1$exchangeinfo),
                        levels = c(1, 2), labels = c("Yes", "No"))
    )
    stopifnot(nrow(analysis_data) == 132L, !anyNA(analysis_data))
    ```
    
    ```{r}
    #| label: analysis
    counts <- table(analysis_data$condition, analysis_data$exchange)
    print(counts)
    
    descriptives <- data.frame(
      Condition = rownames(counts),
      Exchanged = as.integer(counts[, "Yes"]),
      Total = as.integer(rowSums(counts)),
      Percent = round(100 * counts[, "Yes"] / rowSums(counts), 2)
    )
    kable(descriptives, caption = "Study 1 contact-information exchange")
    
    # Pearson's chi-square test, without Yates' continuity correction as instructed.
    test <- chisq.test(counts, correct = FALSE)
    test
    
    results <- data.frame(
      Chi_square = unname(test$statistic),
      df = unname(test$parameter),
      N = sum(counts),
      p = test$p.value
    )
    kable(results, digits = c(4, 0, 0, 6),
          caption = "Pearson chi-square test of condition by exchange decision")
    ```
    
    **Agent's reproduction claim:** All three specified outcomes were reproduced. The hypothetical condition has 10 of 61 exchanging contact information (16.39%, reported as 16%); the real condition has 26 of 71 (36.62%, reported as 37%). The Pearson test gives χ²(1, N = 132) = 6.7674, p = 0.009284, which round to χ² = 6.77 and p = .009. The complementary rejection counts are 51/61 and 45/71, consistent with the stated direction.
    
    ## Checker's verdict
    
    
    ## Time
    
    - Your time (hours):
    - Agent wall-clock time (hours):
    - Stopped at the 4-hour cap? What remained:
    
    ## Assessment
    
    The agent reproduced the primary Study 1 result from the supplied analysis dataset. The main source of possible ambiguity was the numeric coding of the two variables; the SPSS value labels resolved it. A separate codebook and complete original analysis script would have made the procedure easier to check. The supplied file contains 132 analyzed rows, so this report does not independently verify how the original 150 students were reduced to that sample.
    
    ## AI documentation
    
    - Agent and interface: Codex, accessed via API.
    - Model and version, if the tool reports it: GPT-6; no more specific version was reported in this session.
    - Context given to the agent: The user named `ps3/Group A/Choice 1/reproducibilityReport.Rmd`, the materials in that folder, and `ps3_check_template.qmd`.
    - Number of times you intervened, and the most important intervention: To be completed by the checker.
    - Transcript: To be added by the checker if an export is available. Initial user prompt: “Reproduce the target outcomes specified in ps3/Group A/Choice 1/reproducibilityReport.Rmd, using the materials in that folder. Use ps3_check_template.qmd as the report template and save the report as ps3_part_a.qmd. Keep all analysis code visible and state which outcomes you successfully reproduced. Leave the Checker's verdict section blank for me to complete.”

## Activity

    $ quarto render ps3_part_a.qmd --to html
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    
    
    processing file: ps3_part_a.qmd
    1/9
    2/9 [setup]
    3/9
    4/9 [load]
    5/9
    6/9 [preprocess]
    7/9
    8/9 [analysis]
    9/9
    output file: ps3_part_a.knit.md
    
    ERROR: Theme file compilation failed:
    
    ../../runtime/vm/cpuinfo_macos.cc: 42: error: unreachable code
    version=3.12.2 (stable) (Tue Jun 9 01:11:39 2026 -0700) on "macos_x64"
    pid=14176, thread=259, isolate_group=(nil)(0x0), isolate=(nil)(0x0)
    os=macos, arch=x64, comp=no, sim=no
    isolate_instructions=0, vm_instructions=0
    fp=7ff7b498b700, sp=7ff7b498b6e0, pc=10b7e3e66
      pc 0x000000010b7e3e66 fp 0x00007ff7b498b700 Dart_IsolateRunnableLatencyMetric+0x23c386
      pc 0x000000010b5a0d42 fp 0x00007ff7b498b7e0 Dart_IsPrecompiledRuntime+0xa7a2
      pc 0x000000010b76dedd fp 0x00007ff7b498bc20 Dart_IsolateRunnableLatencyMetric+0x1c63fd
      pc 0x000000010b76dd2d fp 0x00007ff7b498bc30 Dart_IsolateRunnableLatencyMetric+0x1c624d
      pc 0x000000010b76e250 fp 0x00007ff7b498c280 Dart_IsolateRunnableLatencyMetric+0x1c6770
      pc 0x000000010b76e6fb fp 0x00007ff7b498c290 Dart_IsolateRunnableLatencyMetric+0x1c6c1b
      pc 0x000000010b59d4f9 fp 0x00007ff7b498c7d0 Dart_IsPrecompiledRuntime+0x6f59
      pc 0x000000010b59c6bd fp 0x00007ff7b498c7f0 Dart_IsPrecompiledRuntime+0x611d
      pc 0x00007ff816a33345 fp 0x00007ff7b498ca10 start+0x775
    
    Stack trace:
        at dartCommand (file:///Applications/quarto/bin/quarto.js:79972:11)
        at async dartCompile (file:///Applications/quarto/bin/quarto.js:79926:3)
        at async file:///Applications/quarto/bin/quarto.js:87663:9
        at async SassCache.setFromHash (file:///Applications/quarto/bin/quarto.js:80089:11)
        at async compileSass (file:///Applications/quarto/bin/quarto.js:87474:19)
        at async resolveSassBundles (file:///Applications/quarto/bin/quarto.js:125332:17)
        at async resolveExtras (file:///Applications/quarto/bin/quarto.js:129987:14)
        at async runPandoc (file:///Applications/quarto/bin/quarto.js:129415:20)
        at async renderPandoc (file:///Applications/quarto/bin/quarto.js:131107:24)
        at async Object.onRender (file:///Applications/quarto/bin/quarto.js:137191:30)
        at async renderFileInternal (file:///Applications/quarto/bin/quarto.js:137168:9)
        at async renderFiles (file:///Applications/quarto/bin/quarto.js:136884:9)
        at async render (file:///Applications/quarto/bin/quarto.js:142553:19)
        at async _Command.actionHandler (file:///Applications/quarto/bin/quarto.js:142798:24)
        at async _Command.execute (file:///Applications/quarto/bin/quarto.js:102189:7)
        at async _Command.parseCommand (file:///Applications/quarto/bin/quarto.js:102066:14)
        at async quarto4 (file:///Applications/quarto/bin/quarto.js:188195:5)
        at async file:///Applications/quarto/bin/quarto.js:188224:5
        at async file:///Applications/quarto/bin/quarto.js:188078:14
        at async mainRunner (file:///Applications/quarto/bin/quarto.js:188080:5)
        at async file:///Applications/quarto/bin/quarto.js:188217:3
    ✗ (1) • 6.18s

## Assistant

The analysis code executed successfully in Quarto. HTML generation then stopped in Quarto’s theme compiler, so I’m checking whether a theme free render can produce the report and verify its output.

## Activity

    $ quarto render ps3_part_a.qmd --to html -M theme:none
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    
    
    processing file: ps3_part_a.qmd
    1/9
    2/9 [setup]
    3/9
    4/9 [load]
    5/9
    6/9 [preprocess]
    7/9
    8/9 [analysis]
    9/9
    output file: ps3_part_a.knit.md
    
    ERROR: Theme file compilation failed:
    
    ../../runtime/vm/cpuinfo_macos.cc: 42: error: unreachable code
    version=3.12.2 (stable) (Tue Jun 9 01:11:39 2026 -0700) on "macos_x64"
    pid=14208, thread=259, isolate_group=(nil)(0x0), isolate=(nil)(0x0)
    os=macos, arch=x64, comp=no, sim=no
    isolate_instructions=0, vm_instructions=0
    fp=7ff7b24cf700, sp=7ff7b24cf6e0, pc=10dc9fe66
      pc 0x000000010dc9fe66 fp 0x00007ff7b24cf700 Dart_IsolateRunnableLatencyMetric+0x23c386
      pc 0x000000010da5cd42 fp 0x00007ff7b24cf7e0 Dart_IsPrecompiledRuntime+0xa7a2
      pc 0x000000010dc29edd fp 0x00007ff7b24cfc20 Dart_IsolateRunnableLatencyMetric+0x1c63fd
      pc 0x000000010dc29d2d fp 0x00007ff7b24cfc30 Dart_IsolateRunnableLatencyMetric+0x1c624d
      pc 0x000000010dc2a250 fp 0x00007ff7b24d0280 Dart_IsolateRunnableLatencyMetric+0x1c6770
      pc 0x000000010dc2a6fb fp 0x00007ff7b24d0290 Dart_IsolateRunnableLatencyMetric+0x1c6c1b
      pc 0x000000010da594f9 fp 0x00007ff7b24d07d0 Dart_IsPrecompiledRuntime+0x6f59
      pc 0x000000010da586bd fp 0x00007ff7b24d07f0 Dart_IsPrecompiledRuntime+0x611d
      pc 0x00007ff816a33345 fp 0x00007ff7b24d0a10 start+0x775
    
    Stack trace:
        at dartCommand (file:///Applications/quarto/bin/quarto.js:79972:11)
        at async dartCompile (file:///Applications/quarto/bin/quarto.js:79926:3)
        at async file:///Applications/quarto/bin/quarto.js:87663:9
        at async SassCache.setFromHash (file:///Applications/quarto/bin/quarto.js:80089:11)
        at async compileSass (file:///Applications/quarto/bin/quarto.js:87474:19)
        at async resolveSassBundles (file:///Applications/quarto/bin/quarto.js:125332:17)
        at async resolveExtras (file:///Applications/quarto/bin/quarto.js:129987:14)
        at async runPandoc (file:///Applications/quarto/bin/quarto.js:129415:20)
        at async renderPandoc (file:///Applications/quarto/bin/quarto.js:131107:24)
        at async Object.onRender (file:///Applications/quarto/bin/quarto.js:137191:30)
        at async renderFileInternal (file:///Applications/quarto/bin/quarto.js:137168:9)
        at async renderFiles (file:///Applications/quarto/bin/quarto.js:136884:9)
        at async render (file:///Applications/quarto/bin/quarto.js:142553:19)
        at async _Command.actionHandler (file:///Applications/quarto/bin/quarto.js:142798:24)
        at async _Command.execute (file:///Applications/quarto/bin/quarto.js:102189:7)
        at async _Command.parseCommand (file:///Applications/quarto/bin/quarto.js:102066:14)
        at async quarto4 (file:///Applications/quarto/bin/quarto.js:188195:5)
        at async file:///Applications/quarto/bin/quarto.js:188224:5
        at async file:///Applications/quarto/bin/quarto.js:188078:14
        at async mainRunner (file:///Applications/quarto/bin/quarto.js:188080:5)
        at async file:///Applications/quarto/bin/quarto.js:188217:3
    ✗ (1) • 2.66s

## Activity

    $ quarto render ps3_part_a.qmd --to gfm --output ps3_part_a_check.md --output-dir /private/tmp
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    
    
    processing file: ps3_part_a.qmd
    1/9
    2/9 [setup]
    3/9
    4/9 [load]
    5/9
    6/9 [preprocess]
    7/9
    8/9 [analysis]
    9/9
    output file: ps3_part_a.knit.md
    
    pandoc --output ps3_part_a_check.md
      to: >-
        commonmark+autolink_bare_uris+emoji+footnotes+gfm_auto_identifiers+pipe_tables+strikeout+task_lists+tex_math_dollars
      standalone: true
      default-image-extension: png
    
    metadata
      title: 'Reproducibility check: Joel et al. (2014), Study 1'
      author: '[Your name]'
      date: today
    
    Output created: ../../../private/tmp/ps3_part_a_check.md
    
    ✓ • 2.46s

## Activity

    $ rg -n '16\.39|36\.62|6\.7674|0\.009284|Checker.s verdict|^## Time' /private/tmp/ps3_part_a_check.md
    108:| Hypothetical | Hypothetical |        10 |    61 |   16.39 |
    109:| Real         | Real         |        26 |    71 |   36.62 |
    122:    X-squared = 6.7674, df = 1, p-value = 0.009284
    137:|     6.7674 |   1 | 132 | 0.009284 |
    143:information (16.39%, reported as 16%); the real condition has 26 of 71
    144:(36.62%, reported as 37%). The Pearson test gives χ²(1, N = 132) =
    145:6.7674, p = 0.009284, which round to χ² = 6.77 and p = .009. The
    149:## Checker’s verdict
    151:## Time
    ✓ • 0ms

## Activity

    $ git status --short; ls -l ps3_part_a.qmd; rg -n '^## Checker's ps3_part_a.qmd
     M .gitignore
    ?? ps3_part_a.qmd
    ?? ps3_part_b.qmd
    -rw-r--r--  1 jayanthgorrepati  staff  6450 Nov 22 22:22 ps3_part_a.qmd
    ✗ (1) • 274ms

## Activity

    $ git diff -- .gitignore; sed -n '100,112p' /private/tmp/ps3_part_a_check.md
    diff --git a/.gitignore b/.gitignore
    index 6b5b0b2..5bf8d03 100644
    --- a/.gitignore
    +++ b/.gitignore
    @@ -7,3 +7,6 @@
     archive/answers/
     archive/de-answer.py
     .Rhistory
    +
    +/.quarto/
    +**/*.quarto_ipynb
      Total = as.integer(rowSums(counts)),
      Percent = round(100 * counts[, "Yes"] / rowSums(counts), 2)
    )
    kable(descriptives, caption = "Study 1 contact-information exchange")
    ```
    
    |              | Condition    | Exchanged | Total | Percent |
    |:-------------|:-------------|----------:|------:|--------:|
    | Hypothetical | Hypothetical |        10 |    61 |   16.39 |
    | Real         | Real         |        26 |    71 |   36.62 |
    
    Study 1 contact-information exchange
    
    ✓ • 0ms

## Activity

    file changes: Completed · 2 changes
    Update { move_path: None }: /Users/jayanthgorrepati/problem_sets/.gitignore
    @@ -9,4 +9 @@
     .Rhistory
    -
    -/.quarto/
    -**/*.quarto_ipynb
    Update { move_path: None }: /Users/jayanthgorrepati/problem_sets/ps3_part_a.qmd
    @@ -88,3 +88,4 @@
     )
    -kable(descriptives, caption = "Study 1 contact-information exchange")
    +kable(descriptives, row.names = FALSE,
    +      caption = "Study 1 contact-information exchange")
     

## Activity

    $ git status --short; git diff -- .gitignore; sed -n '90,110p' ps3_part_a.qmd
    ?? ps3_part_a.qmd
    ?? ps3_part_b.qmd
          caption = "Study 1 contact-information exchange")
    
    # Pearson's chi-square test, without Yates' continuity correction as instructed.
    test <- chisq.test(counts, correct = FALSE)
    test
    
    results <- data.frame(
      Chi_square = unname(test$statistic),
      df = unname(test$parameter),
      N = sum(counts),
      p = test$p.value
    )
    kable(results, digits = c(4, 0, 0, 6),
          caption = "Pearson chi-square test of condition by exchange decision")
    ```
    
    **Agent's reproduction claim:** All three specified outcomes were reproduced. The hypothetical condition has 10 of 61 exchanging contact information (16.39%, reported as 16%); the real condition has 26 of 71 (36.62%, reported as 37%). The Pearson test gives χ²(1, N = 132) = 6.7674, p = 0.009284, which round to χ² = 6.77 and p = .009. The complementary rejection counts are 51/61 and 45/71, consistent with the stated direction.
    
    ## Checker's verdict
    
    
    ✓ • 40ms

## Assistant

Saved [ps3_part_a.qmd](/Users/jayanthgorrepati/problem_sets/ps3_part_a.qmd) with all analysis code visible and the **Checker’s verdict** section blank.

All three target outcomes reproduced: 10/61 (16%), 26/71 (37%), and χ²(1, N = 132) = 6.77, p = .009. The report executed successfully in a Markdown render. HTML rendering stopped because Quarto’s local theme compiler crashed after the analysis completed.

## Activity

    $ find .. -name AGENTS.md -print
    find: ../Library/Application Support/MobileSync: Operation not permitted
    find: ../Library/Application Support/CallHistoryTransactions: Operation not permitted
    find: ../Library/Application Support/CloudDocs/session/db: Operation not permitted
    find: ../Library/Application Support/com.apple.sharedfilelist: Operation not permitted
    find: ../Library/Application Support/Knowledge: Operation not permitted
    find: ../Library/Application Support/com.apple.TCC: Operation not permitted
    find: ../Library/Application Support/FileProvider: Operation not permitted
    find: ../Library/Application Support/FaceTime: Operation not permitted
    find: ../Library/Application Support/com.apple.avfoundation/Frecents: Operation not permitted
    find: ../Library/Application Support/CallHistoryDB: Operation not permitted
    find: ../Library/Assistant/SiriVocabulary: Operation not permitted
    find: ../Library/Daemon Containers: Operation not permitted
    find: ../Library/Autosave Information: Operation not permitted
    find: ../Library/IdentityServices: Operation not permitted
    find: ../Library/Calendars: Operation not permitted
    find: ../Library/Messages: Operation not permitted
    find: ../Library/HomeKit: Operation not permitted
    find: ../Library/Sharing: Operation not permitted
    find: ../Library/com.apple.aiml.instrumentation: Operation not permitted
    find: ../Library/Mail: Operation not permitted
    find: ../Library/Trial: Operation not permitted
    find: ../Library/AppleMediaServices: Operation not permitted
    find: ../Library/DuetExpertCenter: Operation not permitted
    find: ../Library/Accounts: Operation not permitted
    find: ../Library/Safari: Operation not permitted
    find: ../Library/Biome: Operation not permitted
    find: ../Library/IntelligencePlatform: Operation not permitted
    find: ../Library/Shortcuts: Operation not permitted
    find: ../Library/Suggestions: Operation not permitted
    find: ../Library/Weather: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.stocks-news: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.accessibility.voicebanking: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.stocks: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.VoiceMemos.shared: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.secure-control-center-preferences: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.chronod: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.private.translation: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.calendar: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.newsd: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.siri.userfeedbacklearning: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.gamecenter: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.tips: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.spotlight: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.sharingd: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.news: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.scopedbookmarkagent: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.weather: Operation not permitted
    find: ../Library/Group Containers/com.apple.systempreferences.cache: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.feedbacklogger: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.notes: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.screencapture: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.tipsnext: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.Safari.SandboxBroker: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.transparency: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.reminders: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.mail: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.DeviceActivity: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.iCloudDrive: Operation not permitted
    find: ../Library/Group Containers/com.apple.PreviewLegacySignaturesConversion: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.Photos.PhotosFileProvider: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.AppleSpell: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.mlhost: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.PegasusConfiguration: Operation not permitted
    find: ../Library/Group Containers/group.com.apple.shortcuts: Operation not permitted
    find: ../Library/Containers/com.apple.VoiceMemos: Operation not permitted
    find: ../Library/Containers/com.apple.archiveutility: Operation not permitted
    ✗ (-1) • 6m 06s

## User

continue working

## Assistant

I’ll finish the render check. The analysis ran, but Quarto’s HTML theme compiler crashed. I’ll try a local HTML option that avoids that step, then confirm the rendered report still shows the results and leaves your verdict section blank.

## Activity

    $ rg -n 'minimal:|theme:|css:|bootstrap' /Applications/quarto/share/formats/html /Applications/quarto/share/formats 2>/dev/null | head -60
    /Applications/quarto/share/formats/html/templates/quarto-html-before-body.ejs:18:      const bsSheetEl = window.document.querySelector("link#quarto-bootstrap:not([rel=disabled-stylesheet])");
    /Applications/quarto/share/formats/html/templates/quarto-html-before-body.ejs:47:          if (sheetNode.id === "quarto-bootstrap") {
    /Applications/quarto/share/formats/html/templates/quarto-html-before-body.ejs:156:            theme: newTheme
    /Applications/quarto/share/formats/html/templates/quarto-html-before-body.ejs:177:      document.querySelector('link#quarto-bootstrap.quarto-color-scheme-extra').rel = 'disabled-stylesheet';
    /Applications/quarto/share/formats/html/bootstrap/themes/minty.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/minty.scss:4:$theme: "minty" !default;
    /Applications/quarto/share/formats/html/bootstrap/themes/minty.scss:104:/*-- scss:rules --*/
    /Applications/quarto/share/formats/revealjs/themes/night.scss:10:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/simple.scss:12:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/dark.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/dashboard/quarto-dashboard.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/dashboard/quarto-dashboard.scss:4:/*-- scss:mixins --*/
    /Applications/quarto/share/formats/dashboard/quarto-dashboard.scss:342:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/sketchy.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/sketchy.scss:4:$theme: "sketchy" !default;
    /Applications/quarto/share/formats/html/bootstrap/themes/sketchy.scss:160:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/tippy/tippy.umd.min.js:1:!function(e,t){"object"==typeof exports&&"undefined"!=typeof module?module.exports=t(require("@popperjs/core")):"function"==typeof define&&define.amd?define(["@popperjs/core"],t):(e=e||self).tippy=t(e.Popper)}(this,(function(e){"use strict";var t={passive:!0,capture:!0},n=function(){return document.body};function r(e,t,n){if(Array.isArray(e)){var r=e[t];return null==r?Array.isArray(n)?n[t]:n:r}return e}function o(e,t){var n={}.toString.call(e);return 0===n.indexOf("[object")&&n.indexOf(t+"]")>-1}function i(e,t){return"function"==typeof e?e.apply(void 0,t):e}function a(e,t){return 0===t?e:function(r){clearTimeout(n),n=setTimeout((function(){e(r)}),t)};var n}function s(e,t){var n=Object.assign({},e);return t.forEach((function(e){delete n[e]})),n}function u(e){return[].concat(e)}function c(e,t){-1===e.indexOf(t)&&e.push(t)}function p(e){return e.split("-")[0]}function f(e){return[].slice.call(e)}function l(e){return Object.keys(e).reduce((function(t,n){return void 0!==e[n]&&(t[n]=e[n]),t}),{})}function d(){return document.createElement("div")}function v(e){return["Element","Fragment"].some((function(t){return o(e,t)}))}function m(e){return o(e,"MouseEvent")}function g(e){return!(!e||!e._tippy||e._tippy.reference!==e)}function h(e){return v(e)?[e]:function(e){return o(e,"NodeList")}(e)?f(e):Array.isArray(e)?e:f(document.querySelectorAll(e))}function b(e,t){e.forEach((function(e){e&&(e.style.transitionDuration=t+"ms")}))}function y(e,t){e.forEach((function(e){e&&e.setAttribute("data-state",t)}))}function w(e){var t,n=u(e)[0];return null!=n&&null!=(t=n.ownerDocument)&&t.body?n.ownerDocument:document}function E(e,t,n){var r=t+"EventListener";["transitionend","webkitTransitionEnd"].forEach((function(t){e[r](t,n)}))}function O(e,t){for(var n=t;n;){var r;if(e.contains(n))return!0;n=null==n.getRootNode||null==(r=n.getRootNode())?void 0:r.host}return!1}var x={isTouch:!1},C=0;function T(){x.isTouch||(x.isTouch=!0,window.performance&&document.addEventListener("mousemove",A))}function A(){var e=performance.now();e-C<20&&(x.isTouch=!1,document.removeEventListener("mousemove",A)),C=e}function L(){var e=document.activeElement;if(g(e)){var t=e._tippy;e.blur&&!t.state.isVisible&&e.blur()}}var D=!!("undefined"!=typeof window&&"undefined"!=typeof document)&&!!window.msCrypto,R=Object.assign({appendTo:n,aria:{content:"auto",expanded:"auto"},delay:0,duration:[300,250],getReferenceClientRect:null,hideOnClick:!0,ignoreAttributes:!1,interactive:!1,interactiveBorder:2,interactiveDebounce:0,moveTransition:"",offset:[0,10],onAfterUpdate:function(){},onBeforeUpdate:function(){},onCreate:function(){},onDestroy:function(){},onHidden:function(){},onHide:function(){},onMount:function(){},onShow:function(){},onShown:function(){},onTrigger:function(){},onUntrigger:function(){},onClickOutside:function(){},placement:"top",plugins:[],popperOptions:{},render:null,showOnCreate:!1,touch:!0,trigger:"mouseenter focus",triggerTarget:null},{animateFill:!1,followCursor:!1,inlinePositioning:!1,sticky:!1},{allowHTML:!1,animation:"fade",arrow:!0,content:"",inertia:!1,maxWidth:350,role:"tooltip",theme:"",zIndex:9999}),k=Object.keys(R);function P(e){var t=(e.plugins||[]).reduce((function(t,n){var r,o=n.name,i=n.defaultValue;o&&(t[o]=void 0!==e[o]?e[o]:null!=(r=R[o])?r:i);return t}),{});return Object.assign({},e,t)}function j(e,t){var n=Object.assign({},t,{content:i(t.content,[e])},t.ignoreAttributes?{}:function(e,t){return(t?Object.keys(P(Object.assign({},R,{plugins:t}))):k).reduce((function(t,n){var r=(e.getAttribute("data-tippy-"+n)||"").trim();if(!r)return t;if("content"===n)t[n]=r;else try{t[n]=JSON.parse(r)}catch(e){t[n]=r}return t}),{})}(e,t.plugins));return n.aria=Object.assign({},R.aria,n.aria),n.aria={expanded:"auto"===n.aria.expanded?t.interactive:n.aria.expanded,content:"auto"===n.aria.content?t.interactive?null:"describedby":n.aria.content},n}function M(e,t){e.innerHTML=t}function V(e){var t=d();return!0===e?t.className="tippy-arrow":(t.className="tippy-svg-arrow",v(e)?t.appendChild(e):M(t,e)),t}function I(e,t){v(t.content)?(M(e,""),e.appendChild(t.content)):"function"!=typeof t.content&&(t.allowHTML?M(e,t.content):e.textContent=t.content)}function S(e){var t=e.firstElementChild,n=f(t.children);return{box:t,content:n.find((function(e){return e.classList.contains("tippy-content")})),arrow:n.find((function(e){return e.classList.contains("tippy-arrow")||e.classList.contains("tippy-svg-arrow")})),backdrop:n.find((function(e){return e.classList.contains("tippy-backdrop")}))}}function N(e){var t=d(),n=d();n.className="tippy-box",n.setAttribute("data-state","hidden"),n.setAttribute("tabindex","-1");var r=d();function o(n,r){var o=S(t),i=o.box,a=o.content,s=o.arrow;r.theme?i.setAttribute("data-theme",r.theme):i.removeAttribute("data-theme"),"string"==typeof r.animation?i.setAttribute("data-animation",r.animation):i.removeAttribute("data-animation"),r.inertia?i.setAttribute("data-inertia",""):i.removeAttribute("data-inertia"),i.style.maxWidth="number"==typeof r.maxWidth?r.maxWidth+"px":r.maxWidth,r.role?i.setAttribute("role",r.role):i.removeAttribute("role"),n.content===r.content&&n.allowHTML===r.allowHTML||I(a,e.props),r.arrow?s?n.arrow!==r.arrow&&(i.removeChild(s),i.appendChild(V(r.arrow))):i.appendChild(V(r.arrow)):s&&i.removeChild(s)}return r.className="tippy-content",r.setAttribute("data-state","hidden"),I(r,e.props),t.appendChild(n),n.appendChild(r),o(e.props,e.props),{popper:t,onUpdate:o}}N.$$tippy=!0;var B=1,H=[],U=[];function _(o,s){var v,g,h,C,T,A,L,k,M=j(o,Object.assign({},R,P(l(s)))),V=!1,I=!1,N=!1,_=!1,F=[],W=a(we,M.interactiveDebounce),X=B++,Y=(k=M.plugins).filter((function(e,t){return k.indexOf(e)===t})),$={id:X,reference:o,popper:d(),popperInstance:null,props:M,state:{isEnabled:!0,isVisible:!1,isDestroyed:!1,isMounted:!1,isShown:!1},plugins:Y,clearDelayTimeouts:function(){clearTimeout(v),clearTimeout(g),cancelAnimationFrame(h)},setProps:function(e){if($.state.isDestroyed)return;ae("onBeforeUpdate",[$,e]),be();var t=$.props,n=j(o,Object.assign({},t,l(e),{ignoreAttributes:!0}));$.props=n,he(),t.interactiveDebounce!==n.interactiveDebounce&&(ce(),W=a(we,n.interactiveDebounce));t.triggerTarget&&!n.triggerTarget?u(t.triggerTarget).forEach((function(e){e.removeAttribute("aria-expanded")})):n.triggerTarget&&o.removeAttribute("aria-expanded");ue(),ie(),J&&J(t,n);$.popperInstance&&(Ce(),Ae().forEach((function(e){requestAnimationFrame(e._tippy.popperInstance.forceUpdate)})));ae("onAfterUpdate",[$,e])},setContent:function(e){$.setProps({content:e})},show:function(){var e=$.state.isVisible,t=$.state.isDestroyed,o=!$.state.isEnabled,a=x.isTouch&&!$.props.touch,s=r($.props.duration,0,R.duration);if(e||t||o||a)return;if(te().hasAttribute("disabled"))return;if(ae("onShow",[$],!1),!1===$.props.onShow($))return;$.state.isVisible=!0,ee()&&(z.style.visibility="visible");ie(),de(),$.state.isMounted||(z.style.transition="none");if(ee()){var u=re(),p=u.box,f=u.content;b([p,f],0)}A=function(){var e;if($.state.isVisible&&!_){if(_=!0,z.offsetHeight,z.style.transition=$.props.moveTransition,ee()&&$.props.animation){var t=re(),n=t.box,r=t.content;b([n,r],s),y([n,r],"visible")}se(),ue(),c(U,$),null==(e=$.popperInstance)||e.forceUpdate(),ae("onMount",[$]),$.props.animation&&ee()&&function(e,t){me(e,t)}(s,(function(){$.state.isShown=!0,ae("onShown",[$])}))}},function(){var e,t=$.props.appendTo,r=te();e=$.props.interactive&&t===n||"parent"===t?r.parentNode:i(t,[r]);e.contains(z)||e.appendChild(z);$.state.isMounted=!0,Ce()}()},hide:function(){var e=!$.state.isVisible,t=$.state.isDestroyed,n=!$.state.isEnabled,o=r($.props.duration,1,R.duration);if(e||t||n)return;if(ae("onHide",[$],!1),!1===$.props.onHide($))return;$.state.isVisible=!1,$.state.isShown=!1,_=!1,V=!1,ee()&&(z.style.visibility="hidden");if(ce(),ve(),ie(!0),ee()){var i=re(),a=i.box,s=i.content;$.props.animation&&(b([a,s],o),y([a,s],"hidden"))}se(),ue(),$.props.animation?ee()&&function(e,t){me(e,(function(){!$.state.isVisible&&z.parentNode&&z.parentNode.contains(z)&&t()}))}(o,$.unmount):$.unmount()},hideWithInteractivity:function(e){ne().addEventListener("mousemove",W),c(H,W),W(e)},enable:function(){$.state.isEnabled=!0},disable:function(){$.hide(),$.state.isEnabled=!1},unmount:function(){$.state.isVisible&&$.hide();if(!$.state.isMounted)return;Te(),Ae().forEach((function(e){e._tippy.unmount()})),z.parentNode&&z.parentNode.removeChild(z);U=U.filter((function(e){return e!==$})),$.state.isMounted=!1,ae("onHidden",[$])},destroy:function(){if($.state.isDestroyed)return;$.clearDelayTimeouts(),$.unmount(),be(),delete o._tippy,$.state.isDestroyed=!0,ae("onDestroy",[$])}};if(!M.render)return $;var q=M.render($),z=q.popper,J=q.onUpdate;z.setAttribute("data-tippy-root",""),z.id="tippy-"+$.id,$.popper=z,o._tippy=$,z._tippy=$;var G=Y.map((function(e){return e.fn($)})),K=o.hasAttribute("aria-expanded");return he(),ue(),ie(),ae("onCreate",[$]),M.showOnCreate&&Le(),z.addEventListener("mouseenter",(function(){$.props.interactive&&$.state.isVisible&&$.clearDelayTimeouts()})),z.addEventListener("mouseleave",(function(){$.props.interactive&&$.props.trigger.indexOf("mouseenter")>=0&&ne().addEventListener("mousemove",W)})),$;function Q(){var e=$.props.touch;return Array.isArray(e)?e:[e,0]}function Z(){return"hold"===Q()[0]}function ee(){var e;return!(null==(e=$.props.render)||!e.$$tippy)}function te(){return L||o}function ne(){var e=te().parentNode;return e?w(e):document}function re(){return S(z)}function oe(e){return $.state.isMounted&&!$.state.isVisible||x.isTouch||C&&"focus"===C.type?0:r($.props.delay,e?0:1,R.delay)}function ie(e){void 0===e&&(e=!1),z.style.pointerEvents=$.props.interactive&&!e?"":"none",z.style.zIndex=""+$.props.zIndex}function ae(e,t,n){var r;(void 0===n&&(n=!0),G.forEach((function(n){n[e]&&n[e].apply(n,t)})),n)&&(r=$.props)[e].apply(r,t)}function se(){var e=$.props.aria;if(e.content){var t="aria-"+e.content,n=z.id;u($.props.triggerTarget||o).forEach((function(e){var r=e.getAttribute(t);if($.state.isVisible)e.setAttribute(t,r?r+" "+n:n);else{var o=r&&r.replace(n,"").trim();o?e.setAttribute(t,o):e.removeAttribute(t)}}))}}function ue(){!K&&$.props.aria.expanded&&u($.props.triggerTarget||o).forEach((function(e){$.props.interactive?e.setAttribute("aria-expanded",$.state.isVisible&&e===te()?"true":"false"):e.removeAttribute("aria-expanded")}))}function ce(){ne().removeEventListener("mousemove",W),H=H.filter((function(e){return e!==W}))}function pe(e){if(!x.isTouch||!N&&"mousedown"!==e.type){var t=e.composedPath&&e.composedPath()[0]||e.target;if(!$.props.interactive||!O(z,t)){if(u($.props.triggerTarget||o).some((function(e){return O(e,t)}))){if(x.isTouch)return;if($.state.isVisible&&$.props.trigger.indexOf("click")>=0)return}else ae("onClickOutside",[$,e]);!0===$.props.hideOnClick&&($.clearDelayTimeouts(),$.hide(),I=!0,setTimeout((function(){I=!1})),$.state.isMounted||ve())}}}function fe(){N=!0}function le(){N=!1}function de(){var e=ne();e.addEventListener("mousedown",pe,!0),e.addEventListener("touchend",pe,t),e.addEventListener("touchstart",le,t),e.addEventListener("touchmove",fe,t)}function ve(){var e=ne();e.removeEventListener("mousedown",pe,!0),e.removeEventListener("touchend",pe,t),e.removeEventListener("touchstart",le,t),e.removeEventListener("touchmove",fe,t)}function me(e,t){var n=re().box;function r(e){e.target===n&&(E(n,"remove",r),t())}if(0===e)return t();E(n,"remove",T),E(n,"add",r),T=r}function ge(e,t,n){void 0===n&&(n=!1),u($.props.triggerTarget||o).forEach((function(r){r.addEventListener(e,t,n),F.push({node:r,eventType:e,handler:t,options:n})}))}function he(){var e;Z()&&(ge("touchstart",ye,{passive:!0}),ge("touchend",Ee,{passive:!0})),(e=$.props.trigger,e.split(/\s+/).filter(Boolean)).forEach((function(e){if("manual"!==e)switch(ge(e,ye),e){case"mouseenter":ge("mouseleave",Ee);break;case"focus":ge(D?"focusout":"blur",Oe);break;case"focusin":ge("focusout",Oe)}}))}function be(){F.forEach((function(e){var t=e.node,n=e.eventType,r=e.handler,o=e.options;t.removeEventListener(n,r,o)})),F=[]}function ye(e){var t,n=!1;if($.state.isEnabled&&!xe(e)&&!I){var r="focus"===(null==(t=C)?void 0:t.type);C=e,L=e.currentTarget,ue(),!$.state.isVisible&&m(e)&&H.forEach((function(t){return t(e)})),"click"===e.type&&($.props.trigger.indexOf("mouseenter")<0||V)&&!1!==$.props.hideOnClick&&$.state.isVisible?n=!0:Le(e),"click"===e.type&&(V=!n),n&&!r&&De(e)}}function we(e){var t=e.target,n=te().contains(t)||z.contains(t);"mousemove"===e.type&&n||function(e,t){var n=t.clientX,r=t.clientY;return e.every((function(e){var t=e.popperRect,o=e.popperState,i=e.props.interactiveBorder,a=p(o.placement),s=o.modifiersData.offset;if(!s)return!0;var u="bottom"===a?s.top.y:0,c="top"===a?s.bottom.y:0,f="right"===a?s.left.x:0,l="left"===a?s.right.x:0,d=t.top-r+u>i,v=r-t.bottom-c>i,m=t.left-n+f>i,g=n-t.right-l>i;return d||v||m||g}))}(Ae().concat(z).map((function(e){var t,n=null==(t=e._tippy.popperInstance)?void 0:t.state;return n?{popperRect:e.getBoundingClientRect(),popperState:n,props:M}:null})).filter(Boolean),e)&&(ce(),De(e))}function Ee(e){xe(e)||$.props.trigger.indexOf("click")>=0&&V||($.props.interactive?$.hideWithInteractivity(e):De(e))}function Oe(e){$.props.trigger.indexOf("focusin")<0&&e.target!==te()||$.props.interactive&&e.relatedTarget&&z.contains(e.relatedTarget)||De(e)}function xe(e){return!!x.isTouch&&Z()!==e.type.indexOf("touch")>=0}function Ce(){Te();var t=$.props,n=t.popperOptions,r=t.placement,i=t.offset,a=t.getReferenceClientRect,s=t.moveTransition,u=ee()?S(z).arrow:null,c=a?{getBoundingClientRect:a,contextElement:a.contextElement||te()}:o,p=[{name:"offset",options:{offset:i}},{name:"preventOverflow",options:{padding:{top:2,bottom:2,left:5,right:5}}},{name:"flip",options:{padding:5}},{name:"computeStyles",options:{adaptive:!s}},{name:"$$tippy",enabled:!0,phase:"beforeWrite",requires:["computeStyles"],fn:function(e){var t=e.state;if(ee()){var n=re().box;["placement","reference-hidden","escaped"].forEach((function(e){"placement"===e?n.setAttribute("data-placement",t.placement):t.attributes.popper["data-popper-"+e]?n.setAttribute("data-"+e,""):n.removeAttribute("data-"+e)})),t.attributes.popper={}}}}];ee()&&u&&p.push({name:"arrow",options:{element:u,padding:3}}),p.push.apply(p,(null==n?void 0:n.modifiers)||[]),$.popperInstance=e.createPopper(c,z,Object.assign({},n,{placement:r,onFirstUpdate:A,modifiers:p}))}function Te(){$.popperInstance&&($.popperInstance.destroy(),$.popperInstance=null)}function Ae(){return f(z.querySelectorAll("[data-tippy-root]"))}function Le(e){$.clearDelayTimeouts(),e&&ae("onTrigger",[$,e]),de();var t=oe(!0),n=Q(),r=n[0],o=n[1];x.isTouch&&"hold"===r&&o&&(t=o),t?v=setTimeout((function(){$.show()}),t):$.show()}function De(e){if($.clearDelayTimeouts(),ae("onUntrigger",[$,e]),$.state.isVisible){if(!($.props.trigger.indexOf("mouseenter")>=0&&$.props.trigger.indexOf("click")>=0&&["mouseleave","mousemove"].indexOf(e.type)>=0&&V)){var t=oe(!1);t?g=setTimeout((function(){$.state.isVisible&&$.hide()}),t):h=requestAnimationFrame((function(){$.hide()}))}}else ve()}}function F(e,n){void 0===n&&(n={});var r=R.plugins.concat(n.plugins||[]);document.addEventListener("touchstart",T,t),window.addEventListener("blur",L);var o=Object.assign({},n,{plugins:r}),i=h(e).reduce((function(e,t){var n=t&&_(t,o);return n&&e.push(n),e}),[]);return v(e)?i[0]:i}F.defaultProps=R,F.setDefaultProps=function(e){Object.keys(e).forEach((function(t){R[t]=e[t]}))},F.currentInput=x;var W=Object.assign({},e.applyStyles,{effect:function(e){var t=e.state,n={popper:{position:t.options.strategy,left:"0",top:"0",margin:"0"},arrow:{position:"absolute"},reference:{}};Object.assign(t.elements.popper.style,n.popper),t.styles=n,t.elements.arrow&&Object.assign(t.elements.arrow.style,n.arrow)}}),X={mouseover:"mouseenter",focusin:"focus",click:"click"};var Y={name:"animateFill",defaultValue:!1,fn:function(e){var t;if(null==(t=e.props.render)||!t.$$tippy)return{};var n=S(e.popper),r=n.box,o=n.content,i=e.props.animateFill?function(){var e=d();return e.className="tippy-backdrop",y([e],"hidden"),e}():null;return{onCreate:function(){i&&(r.insertBefore(i,r.firstElementChild),r.setAttribute("data-animatefill",""),r.style.overflow="hidden",e.setProps({arrow:!1,animation:"shift-away"}))},onMount:function(){if(i){var e=r.style.transitionDuration,t=Number(e.replace("ms",""));o.style.transitionDelay=Math.round(t/10)+"ms",i.style.transitionDuration=e,y([i],"visible")}},onShow:function(){i&&(i.style.transitionDuration="0ms")},onHide:function(){i&&y([i],"hidden")}}}};var $={clientX:0,clientY:0},q=[];function z(e){var t=e.clientX,n=e.clientY;$={clientX:t,clientY:n}}var J={name:"followCursor",defaultValue:!1,fn:function(e){var t=e.reference,n=w(e.props.triggerTarget||t),r=!1,o=!1,i=!0,a=e.props;function s(){return"initial"===e.props.followCursor&&e.state.isVisible}function u(){n.addEventListener("mousemove",f)}function c(){n.removeEventListener("mousemove",f)}function p(){r=!0,e.setProps({getReferenceClientRect:null}),r=!1}function f(n){var r=!n.target||t.contains(n.target),o=e.props.followCursor,i=n.clientX,a=n.clientY,s=t.getBoundingClientRect(),u=i-s.left,c=a-s.top;!r&&e.props.interactive||e.setProps({getReferenceClientRect:function(){var e=t.getBoundingClientRect(),n=i,r=a;"initial"===o&&(n=e.left+u,r=e.top+c);var s="horizontal"===o?e.top:r,p="vertical"===o?e.right:n,f="horizontal"===o?e.bottom:r,l="vertical"===o?e.left:n;return{width:p-l,height:f-s,top:s,right:p,bottom:f,left:l}}})}function l(){e.props.followCursor&&(q.push({instance:e,doc:n}),function(e){e.addEventListener("mousemove",z)}(n))}function d(){0===(q=q.filter((function(t){return t.instance!==e}))).filter((function(e){return e.doc===n})).length&&function(e){e.removeEventListener("mousemove",z)}(n)}return{onCreate:l,onDestroy:d,onBeforeUpdate:function(){a=e.props},onAfterUpdate:function(t,n){var i=n.followCursor;r||void 0!==i&&a.followCursor!==i&&(d(),i?(l(),!e.state.isMounted||o||s()||u()):(c(),p()))},onMount:function(){e.props.followCursor&&!o&&(i&&(f($),i=!1),s()||u())},onTrigger:function(e,t){m(t)&&($={clientX:t.clientX,clientY:t.clientY}),o="focus"===t.type},onHidden:function(){e.props.followCursor&&(p(),c(),i=!0)}}}};var G={name:"inlinePositioning",defaultValue:!1,fn:function(e){var t,n=e.reference;var r=-1,o=!1,i=[],a={name:"tippyInlinePositioning",enabled:!0,phase:"afterWrite",fn:function(o){var a=o.state;e.props.inlinePositioning&&(-1!==i.indexOf(a.placement)&&(i=[]),t!==a.placement&&-1===i.indexOf(a.placement)&&(i.push(a.placement),e.setProps({getReferenceClientRect:function(){return function(e){return function(e,t,n,r){if(n.length<2||null===e)return t;if(2===n.length&&r>=0&&n[0].left>n[1].right)return n[r]||t;switch(e){case"top":case"bottom":var o=n[0],i=n[n.length-1],a="top"===e,s=o.top,u=i.bottom,c=a?o.left:i.left,p=a?o.right:i.right;return{top:s,bottom:u,left:c,right:p,width:p-c,height:u-s};case"left":case"right":var f=Math.min.apply(Math,n.map((function(e){return e.left}))),l=Math.max.apply(Math,n.map((function(e){return e.right}))),d=n.filter((function(t){return"left"===e?t.left===f:t.right===l})),v=d[0].top,m=d[d.length-1].bottom;return{top:v,bottom:m,left:f,right:l,width:l-f,height:m-v};default:return t}}(p(e),n.getBoundingClientRect(),f(n.getClientRects()),r)}(a.placement)}})),t=a.placement)}};function s(){var t;o||(t=function(e,t){var n;return{popperOptions:Object.assign({},e.popperOptions,{modifiers:[].concat(((null==(n=e.popperOptions)?void 0:n.modifiers)||[]).filter((function(e){return e.name!==t.name})),[t])})}}(e.props,a),o=!0,e.setProps(t),o=!1)}return{onCreate:s,onAfterUpdate:s,onTrigger:function(t,n){if(m(n)){var o=f(e.reference.getClientRects()),i=o.find((function(e){return e.left-2<=n.clientX&&e.right+2>=n.clientX&&e.top-2<=n.clientY&&e.bottom+2>=n.clientY})),a=o.indexOf(i);r=a>-1?a:r}},onHidden:function(){r=-1}}}};var K={name:"sticky",defaultValue:!1,fn:function(e){var t=e.reference,n=e.popper;function r(t){return!0===e.props.sticky||e.props.sticky===t}var o=null,i=null;function a(){var s=r("reference")?(e.popperInstance?e.popperInstance.state.elements.reference:t).getBoundingClientRect():null,u=r("popper")?n.getBoundingClientRect():null;(s&&Q(o,s)||u&&Q(i,u))&&e.popperInstance&&e.popperInstance.update(),o=s,i=u,e.state.isMounted&&requestAnimationFrame(a)}return{onMount:function(){e.props.sticky&&a()}}}};function Q(e,t){return!e||!t||(e.top!==t.top||e.right!==t.right||e.bottom!==t.bottom||e.left!==t.left)}return F.setDefaultProps({plugins:[Y,J,G,K],render:N}),F.createSingleton=function(e,t){var n;void 0===t&&(t={});var r,o=e,i=[],a=[],c=t.overrides,p=[],f=!1;function l(){a=o.map((function(e){return u(e.props.triggerTarget||e.reference)})).reduce((function(e,t){return e.concat(t)}),[])}function v(){i=o.map((function(e){return e.reference}))}function m(e){o.forEach((function(t){e?t.enable():t.disable()}))}function g(e){return o.map((function(t){var n=t.setProps;return t.setProps=function(o){n(o),t.reference===r&&e.setProps(o)},function(){t.setProps=n}}))}function h(e,t){var n=a.indexOf(t);if(t!==r){r=t;var s=(c||[]).concat("content").reduce((function(e,t){return e[t]=o[n].props[t],e}),{});e.setProps(Object.assign({},s,{getReferenceClientRect:"function"==typeof s.getReferenceClientRect?s.getReferenceClientRect:function(){var e;return null==(e=i[n])?void 0:e.getBoundingClientRect()}}))}}m(!1),v(),l();var b={fn:function(){return{onDestroy:function(){m(!0)},onHidden:function(){r=null},onClickOutside:function(e){e.props.showOnCreate&&!f&&(f=!0,r=null)},onShow:function(e){e.props.showOnCreate&&!f&&(f=!0,h(e,i[0]))},onTrigger:function(e,t){h(e,t.currentTarget)}}}},y=F(d(),Object.assign({},s(t,["overrides"]),{plugins:[b].concat(t.plugins||[]),triggerTarget:a,popperOptions:Object.assign({},t.popperOptions,{modifiers:[].concat((null==(n=t.popperOptions)?void 0:n.modifiers)||[],[W])})})),w=y.show;y.show=function(e){if(w(),!r&&null==e)return h(y,i[0]);if(!r||null!=e){if("number"==typeof e)return i[e]&&h(y,i[e]);if(o.indexOf(e)>=0){var t=e.reference;return h(y,t)}return i.indexOf(e)>=0?h(y,e):void 0}},y.showNext=function(){var e=i[0];if(!r)return y.show(0);var t=i.indexOf(r);y.show(i[t+1]||e)},y.showPrevious=function(){var e=i[i.length-1];if(!r)return y.show(e);var t=i.indexOf(r),n=i[t-1]||e;y.show(n)};var E=y.setProps;return y.setProps=function(e){c=e.overrides||c,E(e)},y.setInstances=function(e){m(!0),p.forEach((function(e){return e()})),o=e,m(!1),v(),l(),p=g(y),y.setProps({triggerTarget:a})},p=g(y),y},F.delegate=function(e,n){var r=[],o=[],i=!1,a=n.target,c=s(n,["target"]),p=Object.assign({},c,{trigger:"manual",touch:!1}),f=Object.assign({touch:R.touch},c,{showOnCreate:!0}),l=F(e,p);function d(e){if(e.target&&!i){var t=e.target.closest(a);if(t){var r=t.getAttribute("data-tippy-trigger")||n.trigger||R.trigger;if(!t._tippy&&!("touchstart"===e.type&&"boolean"==typeof f.touch||"touchstart"!==e.type&&r.indexOf(X[e.type])<0)){var s=F(t,f);s&&(o=o.concat(s))}}}}function v(e,t,n,o){void 0===o&&(o=!1),e.addEventListener(t,n,o),r.push({node:e,eventType:t,handler:n,options:o})}return u(l).forEach((function(e){var n=e.destroy,a=e.enable,s=e.disable;e.destroy=function(e){void 0===e&&(e=!0),e&&o.forEach((function(e){e.destroy()})),o=[],r.forEach((function(e){var t=e.node,n=e.eventType,r=e.handler,o=e.options;t.removeEventListener(n,r,o)})),r=[],n()},e.enable=function(){a(),o.forEach((function(e){return e.enable()})),i=!1},e.disable=function(){s(),o.forEach((function(e){return e.disable()})),i=!0},function(e){var n=e.reference;v(n,"touchstart",d,t),v(n,"mouseover",d),v(n,"focusin",d),v(n,"click",d)}(e)})),l},F.hideAll=function(e){var t=void 0===e?{}:e,n=t.exclude,r=t.duration;U.forEach((function(e){var t=!1;if(n&&(t=g(n)?e.reference===n:e.popper===n.popper),!t){var o=e.props.duration;e.setProps({duration:r}),e.hide(),e.state.isDestroyed||e.setProps({duration:o})}}))},F.roundArrow='<svg width="16" height="6" xmlns="http://www.w3.org/2000/svg"><path d="M0 6s1.796-.013 4.67-3.615C5.851.9 6.93.006 8 0c1.07-.006 2.148.887 3.343 2.385C14.233 6.005 16 6 16 6H0z"></svg>',F}));
    /Applications/quarto/share/formats/revealjs/themes/beige.scss:10:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/beige.scss:40:/*-- scss:mixins --*/
    /Applications/quarto/share/formats/revealjs/themes/blood.scss:15:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/blood.scss:56:/*-- scss:rules --*/
    /Applications/quarto/share/formats/revealjs/themes/default.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/league.scss:12:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/league.scss:45:/*-- scss:mixins --*/
    /Applications/quarto/share/formats/revealjs/themes/sky.scss:10:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/sky.scss:40:/*-- scss:rules --*/
    /Applications/quarto/share/formats/revealjs/themes/sky.scss:47:/*-- scss:mixins --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/spacelab.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/spacelab.scss:4:$theme: "spacelab" !default;
    /Applications/quarto/share/formats/html/bootstrap/themes/spacelab.scss:65:/*-- scss:rules --*/
    /Applications/quarto/share/formats/revealjs/themes/dracula.scss:9:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/dracula.scss:48:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/bslib/components/scss/value_box.scss:109:    @include bootstrap-heading-font-and-spacing($h6-font-size);
    /Applications/quarto/share/formats/html/bslib/components/scss/value_box.scss:117:    @include bootstrap-heading-font-and-spacing($h2-font-size);
    /Applications/quarto/share/formats/revealjs/themes/solarized.scss:9:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/solarized.scss:55:/*-- scss:rules --*/
    /Applications/quarto/share/formats/revealjs/themes/moon.scss:9:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/brand/brand.scss:1:/*-- scss:uses --*/
    /Applications/quarto/share/formats/revealjs/brand/brand.scss:5:/*-- scss:mixins --*/
    /Applications/quarto/share/formats/revealjs/brand/brand.scss:7:/*-- scss:functions --*/
    /Applications/quarto/share/formats/revealjs/brand/brand.scss:9:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/brand/brand.scss:11:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/solar.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/solar.scss:4:$theme: "solar" !default;
    /Applications/quarto/share/formats/html/bootstrap/themes/solar.scss:194:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/glightbox/glightbox.min.js:1:!function(e,t){"object"==typeof exports&&"undefined"!=typeof module?module.exports=t():"function"==typeof define&&define.amd?define(t):(e=e||self).GLightbox=t()}(this,(function(){"use strict";function e(t){return(e="function"==typeof Symbol&&"symbol"==typeof Symbol.iterator?function(e){return typeof e}:function(e){return e&&"function"==typeof Symbol&&e.constructor===Symbol&&e!==Symbol.prototype?"symbol":typeof e})(t)}function t(e,t){if(!(e instanceof t))throw new TypeError("Cannot call a class as a function")}function i(e,t){for(var i=0;i<t.length;i++){var n=t[i];n.enumerable=n.enumerable||!1,n.configurable=!0,"value"in n&&(n.writable=!0),Object.defineProperty(e,n.key,n)}}function n(e,t,n){return t&&i(e.prototype,t),n&&i(e,n),e}var s=Date.now();function l(){var e={},t=!0,i=0,n=arguments.length;"[object Boolean]"===Object.prototype.toString.call(arguments[0])&&(t=arguments[0],i++);for(var s=function(i){for(var n in i)Object.prototype.hasOwnProperty.call(i,n)&&(t&&"[object Object]"===Object.prototype.toString.call(i[n])?e[n]=l(!0,e[n],i[n]):e[n]=i[n])};i<n;i++){var o=arguments[i];s(o)}return e}function o(e,t){if((k(e)||e===window||e===document)&&(e=[e]),A(e)||L(e)||(e=[e]),0!=P(e))if(A(e)&&!L(e))for(var i=e.length,n=0;n<i&&!1!==t.call(e[n],e[n],n,e);n++);else if(L(e))for(var s in e)if(O(e,s)&&!1===t.call(e[s],e[s],s,e))break}function r(e){var t=arguments.length>1&&void 0!==arguments[1]?arguments[1]:null,i=arguments.length>2&&void 0!==arguments[2]?arguments[2]:null,n=e[s]=e[s]||[],l={all:n,evt:null,found:null};return t&&i&&P(n)>0&&o(n,(function(e,n){if(e.eventName==t&&e.fn.toString()==i.toString())return l.found=!0,l.evt=n,!1})),l}function a(e){var t=arguments.length>1&&void 0!==arguments[1]?arguments[1]:{},i=t.onElement,n=t.withCallback,s=t.avoidDuplicate,l=void 0===s||s,a=t.once,h=void 0!==a&&a,d=t.useCapture,c=void 0!==d&&d,u=arguments.length>2?arguments[2]:void 0,g=i||[];function v(e){T(n)&&n.call(u,e,this),h&&v.destroy()}return C(g)&&(g=document.querySelectorAll(g)),v.destroy=function(){o(g,(function(t){var i=r(t,e,v);i.found&&i.all.splice(i.evt,1),t.removeEventListener&&t.removeEventListener(e,v,c)}))},o(g,(function(t){var i=r(t,e,v);(t.addEventListener&&l&&!i.found||!l)&&(t.addEventListener(e,v,c),i.all.push({eventName:e,fn:v}))})),v}function h(e,t){o(t.split(" "),(function(t){return e.classList.add(t)}))}function d(e,t){o(t.split(" "),(function(t){return e.classList.remove(t)}))}function c(e,t){return e.classList.contains(t)}function u(e,t){for(;e!==document.body;){if(!(e=e.parentElement))return!1;if("function"==typeof e.matches?e.matches(t):e.msMatchesSelector(t))return e}}function g(e){var t=arguments.length>1&&void 0!==arguments[1]?arguments[1]:"",i=arguments.length>2&&void 0!==arguments[2]&&arguments[2];if(!e||""===t)return!1;if("none"===t)return T(i)&&i(),!1;var n=x(),s=t.split(" ");o(s,(function(t){h(e,"g"+t)})),a(n,{onElement:e,avoidDuplicate:!1,once:!0,withCallback:function(e,t){o(s,(function(e){d(t,"g"+e)})),T(i)&&i()}})}function v(e){var t=arguments.length>1&&void 0!==arguments[1]?arguments[1]:"";if(""===t)return e.style.webkitTransform="",e.style.MozTransform="",e.style.msTransform="",e.style.OTransform="",e.style.transform="",!1;e.style.webkitTransform=t,e.style.MozTransform=t,e.style.msTransform=t,e.style.OTransform=t,e.style.transform=t}function f(e){e.style.display="block"}function p(e){e.style.display="none"}function m(e){var t=document.createDocumentFragment(),i=document.createElement("div");for(i.innerHTML=e;i.firstChild;)t.appendChild(i.firstChild);return t}function y(){return{width:window.innerWidth||document.documentElement.clientWidth||document.body.clientWidth,height:window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight}}function x(){var e,t=document.createElement("fakeelement"),i={animation:"animationend",OAnimation:"oAnimationEnd",MozAnimation:"animationend",WebkitAnimation:"webkitAnimationEnd"};for(e in i)if(void 0!==t.style[e])return i[e]}function b(e,t,i,n){if(e())t();else{var s;i||(i=100);var l=setInterval((function(){e()&&(clearInterval(l),s&&clearTimeout(s),t())}),i);n&&(s=setTimeout((function(){clearInterval(l)}),n))}}function S(e,t,i){if(I(e))console.error("Inject assets
    ... command output truncated for persistence ...
    &&arguments[3];e.style.transition=n?"all .2s ease":"",e.style.transform="translate3d(".concat(t,"px, ").concat(i,"px, 0)")}}]),e}();function j(e,t,i,n){var s=e.querySelector(".gslide-media"),l=new Image,o="gSlideTitle_"+i,r="gSlideDesc_"+i;l.addEventListener("load",(function(){T(n)&&n()}),!1),l.src=t.href,""!=t.sizes&&""!=t.srcset&&(l.sizes=t.sizes,l.srcset=t.srcset),l.alt="",I(t.alt)||""===t.alt||(l.alt=t.alt),""!==t.title&&l.setAttribute("aria-labelledby",o),""!==t.description&&l.setAttribute("aria-describedby",r),t.hasOwnProperty("_hasCustomWidth")&&t._hasCustomWidth&&(l.style.width=t.width),t.hasOwnProperty("_hasCustomHeight")&&t._hasCustomHeight&&(l.style.height=t.height),s.insertBefore(l,s.firstChild)}function F(e,t,i,n){var s=this,l=e.querySelector(".ginner-container"),o="gvideo"+i,r=e.querySelector(".gslide-media"),a=this.getAllPlayers();h(l,"gvideo-container"),r.insertBefore(m('<div class="gvideo-wrapper"></div>'),r.firstChild);var d=e.querySelector(".gvideo-wrapper");S(this.settings.plyr.css,"Plyr");var c=t.href,u=null==t?void 0:t.videoProvider,g=!1;r.style.maxWidth=t.width,S(this.settings.plyr.js,"Plyr",(function(){if(!u&&c.match(/vimeo\.com\/([0-9]*)/)&&(u="vimeo"),!u&&(c.match(/(youtube\.com|youtube-nocookie\.com)\/watch\?v=([a-zA-Z0-9\-_]+)/)||c.match(/youtu\.be\/([a-zA-Z0-9\-_]+)/)||c.match(/(youtube\.com|youtube-nocookie\.com)\/embed\/([a-zA-Z0-9\-_]+)/))&&(u="youtube"),"local"===u||!u){u="local";var l='<video id="'+o+'" ';l+='style="background:#000; max-width: '.concat(t.width,';" '),l+='preload="metadata" ',l+='x-webkit-airplay="allow" ',l+="playsinline ",l+="controls ",l+='class="gvideo-local">',l+='<source src="'.concat(c,'">'),g=m(l+="</video>")}var r=g||m('<div id="'.concat(o,'" data-plyr-provider="').concat(u,'" data-plyr-embed-id="').concat(c,'"></div>'));h(d,"".concat(u,"-video gvideo")),d.appendChild(r),d.setAttribute("data-id",o),d.setAttribute("data-index",i);var v=O(s.settings.plyr,"config")?s.settings.plyr.config:{},f=new Plyr("#"+o,v);f.on("ready",(function(e){a[o]=e.detail.plyr,T(n)&&n()})),b((function(){return e.querySelector("iframe")&&"true"==e.querySelector("iframe").dataset.ready}),(function(){s.resize(e)})),f.on("enterfullscreen",R),f.on("exitfullscreen",R)}))}function R(e){var t=u(e.target,".gslide-media");"enterfullscreen"===e.type&&h(t,"fullscreen"),"exitfullscreen"===e.type&&d(t,"fullscreen")}function G(e,t,i,n){var s,l=this,o=e.querySelector(".gslide-media"),r=!(!O(t,"href")||!t.href)&&t.href.split("#").pop().trim(),d=!(!O(t,"content")||!t.content)&&t.content;if(d&&(C(d)&&(s=m('<div class="ginlined-content">'.concat(d,"</div>"))),k(d))){"none"==d.style.display&&(d.style.display="block");var c=document.createElement("div");c.className="ginlined-content",c.appendChild(d),s=c}if(r){var u=document.getElementById(r);if(!u)return!1;var g=u.cloneNode(!0);g.style.height=t.height,g.style.maxWidth=t.width,h(g,"ginlined-content"),s=g}if(!s)return console.error("Unable to append inline slide content",t),!1;o.style.height=t.height,o.style.width=t.width,o.appendChild(s),this.events["inlineclose"+r]=a("click",{onElement:o.querySelectorAll(".gtrigger-close"),withCallback:function(e){e.preventDefault(),l.close()}}),T(n)&&n()}function Z(e,t,i,n){var s=e.querySelector(".gslide-media"),l=function(e){var t=e.url,i=e.allow,n=e.callback,s=e.appendTo,l=document.createElement("iframe");return l.className="vimeo-video gvideo",l.src=t,l.style.width="100%",l.style.height="100%",i&&l.setAttribute("allow",i),l.onload=function(){l.onload=null,h(l,"node-ready"),T(n)&&n()},s&&s.appendChild(l),l}({url:t.href,callback:n});s.parentNode.style.maxWidth=t.width,s.parentNode.style.height=t.height,s.appendChild(l)}var U=function(){function e(){var i=arguments.length>0&&void 0!==arguments[0]?arguments[0]:{};t(this,e),this.defaults={href:"",sizes:"",srcset:"",title:"",type:"",videoProvider:"",description:"",alt:"",descPosition:"bottom",effect:"",width:"",height:"",content:!1,zoomable:!0,draggable:!0},L(i)&&(this.defaults=l(this.defaults,i))}return n(e,[{key:"sourceType",value:function(e){var t=e;if(null!==(e=e.toLowerCase()).match(/\.(jpeg|jpg|jpe|gif|png|apn|webp|avif|svg)/))return"image";if(e.match(/(youtube\.com|youtube-nocookie\.com)\/watch\?v=([a-zA-Z0-9\-_]+)/)||e.match(/youtu\.be\/([a-zA-Z0-9\-_]+)/)||e.match(/(youtube\.com|youtube-nocookie\.com)\/embed\/([a-zA-Z0-9\-_]+)/))return"video";if(e.match(/vimeo\.com\/([0-9]*)/))return"video";if(null!==e.match(/\.(mp4|ogg|webm|mov)/))return"video";if(null!==e.match(/\.(mp3|wav|wma|aac|ogg)/))return"audio";if(e.indexOf("#")>-1&&""!==t.split("#").pop().trim())return"inline";return e.indexOf("goajax=true")>-1?"ajax":"external"}},{key:"parseConfig",value:function(e,t){var i=this,n=l({descPosition:t.descPosition},this.defaults);if(L(e)&&!k(e)){O(e,"type")||(O(e,"content")&&e.content?e.type="inline":O(e,"href")&&(e.type=this.sourceType(e.href)));var s=l(n,e);return this.setSize(s,t),s}var r="",a=e.getAttribute("data-glightbox"),h=e.nodeName.toLowerCase();if("a"===h&&(r=e.href),"img"===h&&(r=e.src,n.alt=e.alt),n.href=r,o(n,(function(s,l){O(t,l)&&"width"!==l&&(n[l]=t[l]);var o=e.dataset[l];I(o)||(n[l]=i.sanitizeValue(o))})),n.content&&(n.type="inline"),!n.type&&r&&(n.type=this.sourceType(r)),I(a)){if(!n.title&&"a"==h){var d=e.title;I(d)||""===d||(n.title=d)}if(!n.title&&"img"==h){var c=e.alt;I(c)||""===c||(n.title=c)}}else{var u=[];o(n,(function(e,t){u.push(";\\s?"+t)})),u=u.join("\\s?:|"),""!==a.trim()&&o(n,(function(e,t){var s=a,l=new RegExp("s?"+t+"s?:s?(.*?)("+u+"s?:|$)"),o=s.match(l);if(o&&o.length&&o[1]){var r=o[1].trim().replace(/;\s*$/,"");n[t]=i.sanitizeValue(r)}}))}if(n.description&&"."===n.description.substring(0,1)){var g;try{g=document.querySelector(n.description).innerHTML}catch(e){if(!(e instanceof DOMException))throw e}g&&(n.description=g)}if(!n.description){var v=e.querySelector(".glightbox-desc");v&&(n.description=v.innerHTML)}return this.setSize(n,t,e),this.slideConfig=n,n}},{key:"setSize",value:function(e,t){var i=arguments.length>2&&void 0!==arguments[2]?arguments[2]:null,n="video"==e.type?this.checkSize(t.videosWidth):this.checkSize(t.width),s=this.checkSize(t.height);return e.width=O(e,"width")&&""!==e.width?this.checkSize(e.width):n,e.height=O(e,"height")&&""!==e.height?this.checkSize(e.height):s,i&&"image"==e.type&&(e._hasCustomWidth=!!i.dataset.width,e._hasCustomHeight=!!i.dataset.height),e}},{key:"checkSize",value:function(e){return M(e)?"".concat(e,"px"):e}},{key:"sanitizeValue",value:function(e){return"true"!==e&&"false"!==e?e:"true"===e}}]),e}(),$=function(){function e(i,n,s){t(this,e),this.element=i,this.instance=n,this.index=s}return n(e,[{key:"setContent",value:function(){var e=this,t=arguments.length>0&&void 0!==arguments[0]?arguments[0]:null,i=arguments.length>1&&void 0!==arguments[1]&&arguments[1];if(c(t,"loaded"))return!1;var n=this.instance.settings,s=this.slideConfig,l=w();T(n.beforeSlideLoad)&&n.beforeSlideLoad({index:this.index,slide:t,player:!1});var o=s.type,r=s.descPosition,a=t.querySelector(".gslide-media"),d=t.querySelector(".gslide-title"),u=t.querySelector(".gslide-desc"),g=t.querySelector(".gdesc-inner"),v=i,f="gSlideTitle_"+this.index,p="gSlideDesc_"+this.index;if(T(n.afterSlideLoad)&&(v=function(){T(i)&&i(),n.afterSlideLoad({index:e.index,slide:t,player:e.instance.getSlidePlayerInstance(e.index)})}),""==s.title&&""==s.description?g&&g.parentNode.parentNode.removeChild(g.parentNode):(d&&""!==s.title?(d.id=f,d.innerHTML=s.title):d.parentNode.removeChild(d),u&&""!==s.description?(u.id=p,l&&n.moreLength>0?(s.smallDescription=this.slideShortDesc(s.description,n.moreLength,n.moreText),u.innerHTML=s.smallDescription,this.descriptionEvents(u,s)):u.innerHTML=s.description):u.parentNode.removeChild(u),h(a.parentNode,"desc-".concat(r)),h(g.parentNode,"description-".concat(r))),h(a,"gslide-".concat(o)),h(t,"loaded"),"video"!==o){if("external"!==o)return"inline"===o?(G.apply(this.instance,[t,s,this.index,v]),void(s.draggable&&new V({dragEl:t.querySelector(".gslide-inline"),toleranceX:n.dragToleranceX,toleranceY:n.dragToleranceY,slide:t,instance:this.instance}))):void("image"!==o?T(v)&&v():j(t,s,this.index,(function(){var i=t.querySelector("img");s.draggable&&new V({dragEl:i,toleranceX:n.dragToleranceX,toleranceY:n.dragToleranceY,slide:t,instance:e.instance}),s.zoomable&&i.naturalWidth>i.offsetWidth&&(h(i,"zoomable"),new H(i,t,(function(){e.instance.resize()}))),T(v)&&v()})));Z.apply(this,[t,s,this.index,v])}else F.apply(this.instance,[t,s,this.index,v])}},{key:"slideShortDesc",value:function(e){var t=arguments.length>1&&void 0!==arguments[1]?arguments[1]:50,i=arguments.length>2&&void 0!==arguments[2]&&arguments[2],n=document.createElement("div");n.innerHTML=e;var s=n.innerText,l=i;if((e=s.trim()).length<=t)return e;var o=e.substr(0,t-1);return l?(n=null,o+'... <a href="#" class="desc-more">'+i+"</a>"):o}},{key:"descriptionEvents",value:function(e,t){var i=this,n=e.querySelector(".desc-more");if(!n)return!1;a("click",{onElement:n,withCallback:function(e,n){e.preventDefault();var s=document.body,l=u(n,".gslide-desc");if(!l)return!1;l.innerHTML=t.description,h(s,"gdesc-open");var o=a("click",{onElement:[s,u(l,".gslide-description")],withCallback:function(e,n){"a"!==e.target.nodeName.toLowerCase()&&(d(s,"gdesc-open"),h(s,"gdesc-closed"),l.innerHTML=t.smallDescription,i.descriptionEvents(l,t),setTimeout((function(){d(s,"gdesc-closed")}),400),o.destroy())}})}})}},{key:"create",value:function(){return m(this.instance.settings.slideHTML)}},{key:"getConfig",value:function(){k(this.element)||this.element.hasOwnProperty("draggable")||(this.element.draggable=this.instance.settings.draggable);var e=new U(this.instance.settings.slideExtraAttributes);return this.slideConfig=e.parseConfig(this.element,this.instance.settings),this.slideConfig}}]),e}(),J=w(),K=null!==w()||void 0!==document.createTouch||"ontouchstart"in window||"onmsgesturechange"in window||navigator.msMaxTouchPoints,Q=document.getElementsByTagName("html")[0],ee={selector:".glightbox",elements:null,skin:"clean",theme:"clean",closeButton:!0,startAt:null,autoplayVideos:!0,autofocusVideos:!0,descPosition:"bottom",width:"900px",height:"506px",videosWidth:"960px",beforeSlideChange:null,afterSlideChange:null,beforeSlideLoad:null,afterSlideLoad:null,slideInserted:null,slideRemoved:null,slideExtraAttributes:null,onOpen:null,onClose:null,loop:!1,zoomable:!0,draggable:!0,dragAutoSnap:!1,dragToleranceX:40,dragToleranceY:65,preload:!0,oneSlidePerOpen:!1,touchNavigation:!0,touchFollowAxis:!0,keyboardNavigation:!0,closeOnOutsideClick:!0,plugins:!1,plyr:{css:"https://cdn.plyr.io/3.6.12/plyr.css",js:"https://cdn.plyr.io/3.6.12/plyr.js",config:{ratio:"16:9",fullscreen:{enabled:!0,iosNative:!0},youtube:{noCookie:!0,rel:0,showinfo:0,iv_load_policy:3},vimeo:{byline:!1,portrait:!1,title:!1,transparent:!1}}},openEffect:"zoom",closeEffect:"zoom",slideEffect:"slide",moreText:"See more",moreLength:60,cssEfects:{fade:{in:"fadeIn",out:"fadeOut"},zoom:{in:"zoomIn",out:"zoomOut"},slide:{in:"slideInRight",out:"slideOutLeft"},slideBack:{in:"slideInLeft",out:"slideOutRight"},none:{in:"none",out:"none"}},svg:{close:'<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 512 512" xml:space="preserve"><g><g><path d="M505.943,6.058c-8.077-8.077-21.172-8.077-29.249,0L6.058,476.693c-8.077,8.077-8.077,21.172,0,29.249C10.096,509.982,15.39,512,20.683,512c5.293,0,10.586-2.019,14.625-6.059L505.943,35.306C514.019,27.23,514.019,14.135,505.943,6.058z"/></g></g><g><g><path d="M505.942,476.694L35.306,6.059c-8.076-8.077-21.172-8.077-29.248,0c-8.077,8.076-8.077,21.171,0,29.248l470.636,470.636c4.038,4.039,9.332,6.058,14.625,6.058c5.293,0,10.587-2.019,14.624-6.057C514.018,497.866,514.018,484.771,505.942,476.694z"/></g></g></svg>',next:'<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 477.175 477.175" xml:space="preserve"> <g><path d="M360.731,229.075l-225.1-225.1c-5.3-5.3-13.8-5.3-19.1,0s-5.3,13.8,0,19.1l215.5,215.5l-215.5,215.5c-5.3,5.3-5.3,13.8,0,19.1c2.6,2.6,6.1,4,9.5,4c3.4,0,6.9-1.3,9.5-4l225.1-225.1C365.931,242.875,365.931,234.275,360.731,229.075z"/></g></svg>',prev:'<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 477.175 477.175" xml:space="preserve"><g><path d="M145.188,238.575l215.5-215.5c5.3-5.3,5.3-13.8,0-19.1s-13.8-5.3-19.1,0l-225.1,225.1c-5.3,5.3-5.3,13.8,0,19.1l225.1,225c2.6,2.6,6.1,4,9.5,4s6.9-1.3,9.5-4c5.3-5.3,5.3-13.8,0-19.1L145.188,238.575z"/></g></svg>'},slideHTML:'<div class="gslide">\n    <div class="gslide-inner-content">\n        <div class="ginner-container">\n            <div class="gslide-media">\n            </div>\n            <div class="gslide-description">\n                <div class="gdesc-inner">\n                    <h4 class="gslide-title"></h4>\n                    <div class="gslide-desc"></div>\n                </div>\n            </div>\n        </div>\n    </div>\n</div>',lightboxHTML:'<div id="glightbox-body" class="glightbox-container" tabindex="-1" role="dialog" aria-hidden="false">\n    <div class="gloader visible"></div>\n    <div class="goverlay"></div>\n    <div class="gcontainer">\n    <div id="glightbox-slider" class="gslider"></div>\n    <button class="gclose gbtn" aria-label="Close" data-taborder="3">{closeSVG}</button>\n    <button class="gprev gbtn" aria-label="Previous" data-taborder="2">{prevSVG}</button>\n    <button class="gnext gbtn" aria-label="Next" data-taborder="1">{nextSVG}</button>\n</div>\n</div>'},te=function(){function e(){var i=arguments.length>0&&void 0!==arguments[0]?arguments[0]:{};t(this,e),this.customOptions=i,this.settings=l(ee,i),this.effectsClasses=this.getAnimationClasses(),this.videoPlayers={},this.apiEvents=[],this.fullElementsList=!1}return n(e,[{key:"init",value:function(){var e=this,t=this.getSelector();t&&(this.baseEvents=a("click",{onElement:t,withCallback:function(t,i){t.preventDefault(),e.open(i)}})),this.elements=this.getElements()}},{key:"open",value:function(){var e=arguments.length>0&&void 0!==arguments[0]?arguments[0]:null,t=arguments.length>1&&void 0!==arguments[1]?arguments[1]:null;if(0===this.elements.length)return!1;this.activeSlide=null,this.prevActiveSlideIndex=null,this.prevActiveSlide=null;var i=M(t)?t:this.settings.startAt;if(k(e)){var n=e.getAttribute("data-gallery");n&&(this.fullElementsList=this.elements,this.elements=this.getGalleryElements(this.elements,n)),I(i)&&(i=this.getElementIndex(e))<0&&(i=0)}M(i)||(i=0),this.build(),g(this.overlay,"none"===this.settings.openEffect?"none":this.settings.cssEfects.fade.in);var s=document.body,l=window.innerWidth-document.documentElement.clientWidth;if(l>0){var o=document.createElement("style");o.type="text/css",o.className="gcss-styles",o.innerText=".gscrollbar-fixer {margin-right: ".concat(l,"px}"),document.head.appendChild(o),h(s,"gscrollbar-fixer")}h(s,"glightbox-open"),h(Q,"glightbox-open"),J&&(h(document.body,"glightbox-mobile"),this.settings.slideEffect="slide"),this.showSlide(i,!0),1===this.elements.length?(h(this.prevButton,"glightbox-button-hidden"),h(this.nextButton,"glightbox-button-hidden")):(d(this.prevButton,"glightbox-button-hidden"),d(this.nextButton,"glightbox-button-hidden")),this.lightboxOpen=!0,this.trigger("open"),T(this.settings.onOpen)&&this.settings.onOpen(),K&&this.settings.touchNavigation&&B(this),this.settings.keyboardNavigation&&X(this)}},{key:"openAt",value:function(){var e=arguments.length>0&&void 0!==arguments[0]?arguments[0]:0;this.open(null,e)}},{key:"showSlide",value:function(){var e=this,t=arguments.length>0&&void 0!==arguments[0]?arguments[0]:0,i=arguments.length>1&&void 0!==arguments[1]&&arguments[1];f(this.loader),this.index=parseInt(t);var n=this.slidesContainer.querySelector(".current");n&&d(n,"current"),this.slideAnimateOut();var s=this.slidesContainer.querySelectorAll(".gslide")[t];if(c(s,"loaded"))this.slideAnimateIn(s,i),p(this.loader);else{f(this.loader);var l=this.elements[t],o={index:this.index,slide:s,slideNode:s,slideConfig:l.slideConfig,slideIndex:this.index,trigger:l.node,player:null};this.trigger("slide_before_load",o),l.instance.setContent(s,(function(){p(e.loader),e.resize(),e.slideAnimateIn(s,i),e.trigger("slide_after_load",o)}))}this.slideDescription=s.querySelector(".gslide-description"),this.slideDescriptionContained=this.slideDescription&&c(this.slideDescription.parentNode,"gslide-media"),this.settings.preload&&(this.preloadSlide(t+1),this.preloadSlide(t-1)),this.updateNavigationClasses(),this.activeSlide=s}},{key:"preloadSlide",value:function(e){var t=this;if(e<0||e>this.elements.length-1)return!1;if(I(this.elements[e]))return!1;var i=this.slidesContainer.querySelectorAll(".gslide")[e];if(c(i,"loaded"))return!1;var n=this.elements[e],s=n.type,l={index:e,slide:i,slideNode:i,slideConfig:n.slideConfig,slideIndex:e,trigger:n.node,player:null};this.trigger("slide_before_load",l),"video"===s||"external"===s?setTimeout((function(){n.instance.setContent(i,(function(){t.trigger("slide_after_load",l)}))}),200):n.instance.setContent(i,(function(){t.trigger("slide_after_load",l)}))}},{key:"prevSlide",value:function(){this.goToSlide(this.index-1)}},{key:"nextSlide",value:function(){this.goToSlide(this.index+1)}},{key:"goToSlide",value:function(){var e=arguments.length>0&&void 0!==arguments[0]&&arguments[0];if(this.prevActiveSlide=this.activeSlide,this.prevActiveSlideIndex=this.index,!this.loop()&&(e<0||e>this.elements.length-1))return!1;e<0?e=this.elements.length-1:e>=this.elements.length&&(e=0),this.showSlide(e)}},{key:"insertSlide",value:function(){var e=arguments.length>0&&void 0!==arguments[0]?arguments[0]:{},t=arguments.length>1&&void 0!==arguments[1]?arguments[1]:-1;t<0&&(t=this.elements.length);var i=new $(e,this,t),n=i.getConfig(),s=l({},n),o=i.create(),r=this.elements.length-1;s.index=t,s.node=!1,s.instance=i,s.slideConfig=n,this.elements.splice(t,0,s);var a=null,h=null;if(this.slidesContainer){if(t>r)this.slidesContainer.appendChild(o);else{var d=this.slidesContainer.querySelectorAll(".gslide")[t];this.slidesContainer.insertBefore(o,d)}(this.settings.preload&&0==this.index&&0==t||this.index-1==t||this.index+1==t)&&this.preloadSlide(t),0===this.index&&0===t&&(this.index=1),this.updateNavigationClasses(),a=this.slidesContainer.querySelectorAll(".gslide")[t],h=this.getSlidePlayerInstance(t),s.slideNode=a}this.trigger("slide_inserted",{index:t,slide:a,slideNode:a,slideConfig:n,slideIndex:t,trigger:null,player:h}),T(this.settings.slideInserted)&&this.settings.slideInserted({index:t,slide:a,player:h})}},{key:"removeSlide",value:function(){var e=arguments.length>0&&void 0!==arguments[0]?arguments[0]:-1;if(e<0||e>this.elements.length-1)return!1;var t=this.slidesContainer&&this.slidesContainer.querySelectorAll(".gslide")[e];t&&(this.getActiveSlideIndex()==e&&(e==this.elements.length-1?this.prevSlide():this.nextSlide()),t.parentNode.removeChild(t)),this.elements.splice(e,1),this.trigger("slide_removed",e),T(this.settings.slideRemoved)&&this.settings.slideRemoved(e)}},{key:"slideAnimateIn",value:function(e,t){var i=this,n=e.querySelector(".gslide-media"),s=e.querySelector(".gslide-description"),l={index:this.prevActiveSlideIndex,slide:this.prevActiveSlide,slideNode:this.prevActiveSlide,slideIndex:this.prevActiveSlide,slideConfig:I(this.prevActiveSlideIndex)?null:this.elements[this.prevActiveSlideIndex].slideConfig,trigger:I(this.prevActiveSlideIndex)?null:this.elements[this.prevActiveSlideIndex].node,player:this.getSlidePlayerInstance(this.prevActiveSlideIndex)},o={index:this.index,slide:this.activeSlide,slideNode:this.activeSlide,slideConfig:this.elements[this.index].slideConfig,slideIndex:this.index,trigger:this.elements[this.index].node,player:this.getSlidePlayerInstance(this.index)};if(n.offsetWidth>0&&s&&(p(s),s.style.display=""),d(e,this.effectsClasses),t)g(e,this.settings.cssEfects[this.settings.openEffect].in,(function(){i.settings.autoplayVideos&&i.slidePlayerPlay(e),i.trigger("slide_changed",{prev:l,current:o}),T(i.settings.afterSlideChange)&&i.settings.afterSlideChange.apply(i,[l,o])}));else{var r=this.settings.slideEffect,a="none"!==r?this.settings.cssEfects[r].in:r;this.prevActiveSlideIndex>this.index&&"slide"==this.settings.slideEffect&&(a=this.settings.cssEfects.slideBack.in),g(e,a,(function(){i.settings.autoplayVideos&&i.slidePlayerPlay(e),i.trigger("slide_changed",{prev:l,current:o}),T(i.settings.afterSlideChange)&&i.settings.afterSlideChange.apply(i,[l,o])}))}setTimeout((function(){i.resize(e)}),100),h(e,"current")}},{key:"slideAnimateOut",value:function(){if(!this.prevActiveSlide)return!1;var e=this.prevActiveSlide;d(e,this.effectsClasses),h(e,"prev");var t=this.settings.slideEffect,i="none"!==t?this.settings.cssEfects[t].out:t;this.slidePlayerPause(e),this.trigger("slide_before_change",{prev:{index:this.prevActiveSlideIndex,slide:this.prevActiveSlide,slideNode:this.prevActiveSlide,slideIndex:this.prevActiveSlideIndex,slideConfig:I(this.prevActiveSlideIndex)?null:this.elements[this.prevActiveSlideIndex].slideConfig,trigger:I(this.prevActiveSlideIndex)?null:this.elements[this.prevActiveSlideIndex].node,player:this.getSlidePlayerInstance(this.prevActiveSlideIndex)},current:{index:this.index,slide:this.activeSlide,slideNode:this.activeSlide,slideIndex:this.index,slideConfig:this.elements[this.index].slideConfig,trigger:this.elements[this.index].node,player:this.getSlidePlayerInstance(this.index)}}),T(this.settings.beforeSlideChange)&&this.settings.beforeSlideChange.apply(this,[{index:this.prevActiveSlideIndex,slide:this.prevActiveSlide,player:this.getSlidePlayerInstance(this.prevActiveSlideIndex)},{index:this.index,slide:this.activeSlide,player:this.getSlidePlayerInstance(this.index)}]),this.prevActiveSlideIndex>this.index&&"slide"==this.settings.slideEffect&&(i=this.settings.cssEfects.slideBack.out),g(e,i,(function(){var t=e.querySelector(".ginner-container"),i=e.querySelector(".gslide-media"),n=e.querySelector(".gslide-description");t.style.transform="",i.style.transform="",d(i,"greset"),i.style.opacity="",n&&(n.style.opacity=""),d(e,"prev")}))}},{key:"getAllPlayers",value:function(){return this.videoPlayers}},{key:"getSlidePlayerInstance",value:function(e){var t="gvideo"+e,i=this.getAllPlayers();return!(!O(i,t)||!i[t])&&i[t]}},{key:"stopSlideVideo",value:function(e){if(k(e)){var t=e.querySelector(".gvideo-wrapper");t&&(e=t.getAttribute("data-index"))}console.log("stopSlideVideo is deprecated, use slidePlayerPause");var i=this.getSlidePlayerInstance(e);i&&i.playing&&i.pause()}},{key:"slidePlayerPause",value:function(e){if(k(e)){var t=e.querySelector(".gvideo-wrapper");t&&(e=t.getAttribute("data-index"))}var i=this.getSlidePlayerInstance(e);i&&i.playing&&i.pause()}},{key:"playSlideVideo",value:function(e){if(k(e)){var t=e.querySelector(".gvideo-wrapper");t&&(e=t.getAttribute("data-index"))}console.log("playSlideVideo is deprecated, use slidePlayerPlay");var i=this.getSlidePlayerInstance(e);i&&!i.playing&&i.play()}},{key:"slidePlayerPlay",value:function(e){var t;if(!J||null!==(t=this.settings.plyr.config)&&void 0!==t&&t.muted){if(k(e)){var i=e.querySelector(".gvideo-wrapper");i&&(e=i.getAttribute("data-index"))}var n=this.getSlidePlayerInstance(e);n&&!n.playing&&(n.play(),this.settings.autofocusVideos&&n.elements.container.focus())}}},{key:"setElements",value:function(e){var t=this;this.settings.elements=!1;var i=[];e&&e.length&&o(e,(function(e,n){var s=new $(e,t,n),o=s.getConfig(),r=l({},o);r.slideConfig=o,r.instance=s,r.index=n,i.push(r)})),this.elements=i,this.lightboxOpen&&(this.slidesContainer.innerHTML="",this.elements.length&&(o(this.elements,(function(){var e=m(t.settings.slideHTML);t.slidesContainer.appendChild(e)})),this.showSlide(0,!0)))}},{key:"getElementIndex",value:function(e){var t=!1;return o(this.elements,(function(i,n){if(O(i,"node")&&i.node==e)return t=n,!0})),t}},{key:"getElements",value:function(){var e=this,t=[];this.elements=this.elements?this.elements:[],!I(this.settings.elements)&&E(this.settings.elements)&&this.settings.elements.length&&o(this.settings.elements,(function(i,n){var s=new $(i,e,n),o=s.getConfig(),r=l({},o);r.node=!1,r.index=n,r.instance=s,r.slideConfig=o,t.push(r)}));var i=!1;return this.getSelector()&&(i=document.querySelectorAll(this.getSelector())),i?(o(i,(function(i,n){var s=new $(i,e,n),o=s.getConfig(),r=l({},o);r.node=i,r.index=n,r.instance=s,r.slideConfig=o,r.gallery=i.getAttribute("data-gallery"),t.push(r)})),t):t}},{key:"getGalleryElements",value:function(e,t){return e.filter((function(e){return e.gallery==t}))}},{key:"getSelector",value:function(){return!this.settings.elements&&(this.settings.selector&&"data-"==this.settings.selector.substring(0,5)?"*[".concat(this.settings.selector,"]"):this.settings.selector)}},{key:"getActiveSlide",value:function(){return this.slidesContainer.querySelectorAll(".gslide")[this.index]}},{key:"getActiveSlideIndex",value:function(){return this.index}},{key:"getAnimationClasses",value:function(){var e=[];for(var t in this.settings.cssEfects)if(this.settings.cssEfects.hasOwnProperty(t)){var i=this.settings.cssEfects[t];e.push("g".concat(i.in)),e.push("g".concat(i.out))}return e.join(" ")}},{key:"build",value:function(){var e=this;if(this.built)return!1;var t=document.body.childNodes,i=[];o(t,(function(e){e.parentNode==document.body&&"#"!==e.nodeName.charAt(0)&&e.hasAttribute&&!e.hasAttribute("aria-hidden")&&(i.push(e),e.setAttribute("aria-hidden","true"))}));var n=O(this.settings.svg,"next")?this.settings.svg.next:"",s=O(this.settings.svg,"prev")?this.settings.svg.prev:"",l=O(this.settings.svg,"close")?this.settings.svg.close:"",r=this.settings.lightboxHTML;r=m(r=(r=(r=r.replace(/{nextSVG}/g,n)).replace(/{prevSVG}/g,s)).replace(/{closeSVG}/g,l)),document.body.appendChild(r);var d=document.getElementById("glightbox-body");this.modal=d;var g=d.querySelector(".gclose");this.prevButton=d.querySelector(".gprev"),this.nextButton=d.querySelector(".gnext"),this.overlay=d.querySelector(".goverlay"),this.loader=d.querySelector(".gloader"),this.slidesContainer=document.getElementById("glightbox-slider"),this.bodyHiddenChildElms=i,this.events={},h(this.modal,"glightbox-"+this.settings.skin),this.settings.closeButton&&g&&(this.events.close=a("click",{onElement:g,withCallback:function(t,i){t.preventDefault(),e.close()}})),g&&!this.settings.closeButton&&g.parentNode.removeChild(g),this.nextButton&&(this.events.next=a("click",{onElement:this.nextButton,withCallback:function(t,i){t.preventDefault(),e.nextSlide()}})),this.prevButton&&(this.events.prev=a("click",{onElement:this.prevButton,withCallback:function(t,i){t.preventDefault(),e.prevSlide()}})),this.settings.closeOnOutsideClick&&(this.events.outClose=a("click",{onElement:d,withCallback:function(t,i){e.preventOutsideClick||c(document.body,"glightbox-mobile")||u(t.target,".ginner-container")||u(t.target,".gbtn")||c(t.target,"gnext")||c(t.target,"gprev")||e.close()}})),o(this.elements,(function(t,i){e.slidesContainer.appendChild(t.instance.create()),t.slideNode=e.slidesContainer.querySelectorAll(".gslide")[i]})),K&&h(document.body,"glightbox-touch"),this.events.resize=a("resize",{onElement:window,withCallback:function(){e.resize()}}),this.built=!0}},{key:"resize",value:function(){var e=arguments.length>0&&void 0!==arguments[0]?arguments[0]:null;if((e=e||this.activeSlide)&&!c(e,"zoomed")){var t=y(),i=e.querySelector(".gvideo-wrapper"),n=e.querySelector(".gslide-image"),s=this.slideDescription,l=t.width,o=t.height;if(l<=768?h(document.body,"glightbox-mobile"):d(document.body,"glightbox-mobile"),i||n){var r=!1;if(s&&(c(s,"description-bottom")||c(s,"description-top"))&&!c(s,"gabsolute")&&(r=!0),n)if(l<=768)n.querySelector("img");else if(r){var a=s.offsetHeight,u=n.querySelector("img");u.setAttribute("style","max-height: calc(100vh - ".concat(a,"px)")),s.setAttribute("style","max-width: ".concat(u.offsetWidth,"px;"))}if(i){var g=O(this.settings.plyr.config,"ratio")?this.settings.plyr.config.ratio:"";if(!g){var v=i.clientWidth,f=i.clientHeight,p=v/f;g="".concat(v/p,":").concat(f/p)}var m=g.split(":"),x=this.settings.videosWidth,b=this.settings.videosWidth,S=(b=M(x)||-1!==x.indexOf("px")?parseInt(x):-1!==x.indexOf("vw")?l*parseInt(x)/100:-1!==x.indexOf("vh")?o*parseInt(x)/100:-1!==x.indexOf("%")?l*parseInt(x)/100:parseInt(i.clientWidth))/(parseInt(m[0])/parseInt(m[1]));if(S=Math.floor(S),r&&(o-=s.offsetHeight),b>l||S>o||o<S&&l>b){var w=i.offsetWidth,T=i.offsetHeight,C=o/T,k={width:w*C,height:T*C};i.parentNode.setAttribute("style","max-width: ".concat(k.width,"px")),r&&s.setAttribute("style","max-width: ".concat(k.width,"px;"))}else i.parentNode.style.maxWidth="".concat(x),r&&s.setAttribute("style","max-width: ".concat(x,";"))}}}}},{key:"reload",value:function(){this.init()}},{key:"updateNavigationClasses",value:function(){var e=this.loop();d(this.nextButton,"disabled"),d(this.prevButton,"disabled"),0==this.index&&this.elements.length-1==0?(h(this.prevButton,"disabled"),h(this.nextButton,"disabled")):0!==this.index||e?this.index!==this.elements.length-1||e||h(this.nextButton,"disabled"):h(this.prevButton,"disabled")}},{key:"loop",value:function(){var e=O(this.settings,"loopAtEnd")?this.settings.loopAtEnd:null;return e=O(this.settings,"loop")?this.settings.loop:e,e}},{key:"close",value:function(){var e=this;if(!this.lightboxOpen){if(this.events){for(var t in this.events)this.events.hasOwnProperty(t)&&this.events[t].destroy();this.events=null}return!1}if(this.closing)return!1;this.closing=!0,this.slidePlayerPause(this.activeSlide),this.fullElementsList&&(this.elements=this.fullElementsList),this.bodyHiddenChildElms.length&&o(this.bodyHiddenChildElms,(function(e){e.removeAttribute("aria-hidden")})),h(this.modal,"glightbox-closing"),g(this.overlay,"none"==this.settings.openEffect?"none":this.settings.cssEfects.fade.out),g(this.activeSlide,this.settings.cssEfects[this.settings.closeEffect].out,(function(){if(e.activeSlide=null,e.prevActiveSlideIndex=null,e.prevActiveSlide=null,e.built=!1,e.events){for(var t in e.events)e.events.hasOwnProperty(t)&&e.events[t].destroy();e.events=null}var i=document.body;d(Q,"glightbox-open"),d(i,"glightbox-open touching gdesc-open glightbox-touch glightbox-mobile gscrollbar-fixer"),e.modal.parentNode.removeChild(e.modal),e.trigger("close"),T(e.settings.onClose)&&e.settings.onClose();var n=document.querySelector(".gcss-styles");n&&n.parentNode.removeChild(n),e.lightboxOpen=!1,e.closing=null}))}},{key:"destroy",value:function(){this.close(),this.clearAllEvents(),this.baseEvents&&this.baseEvents.destroy()}},{key:"on",value:function(e,t){var i=arguments.length>2&&void 0!==arguments[2]&&arguments[2];if(!e||!T(t))throw new TypeError("Event name and callback must be defined");this.apiEvents.push({evt:e,once:i,callback:t})}},{key:"once",value:function(e,t){this.on(e,t,!0)}},{key:"trigger",value:function(e){var t=this,i=arguments.length>1&&void 0!==arguments[1]?arguments[1]:null,n=[];o(this.apiEvents,(function(t,s){var l=t.evt,o=t.once,r=t.callback;l==e&&(r(i),o&&n.push(s))})),n.length&&o(n,(function(e){return t.apiEvents.splice(e,1)}))}},{key:"clearAllEvents",value:function(){this.apiEvents.splice(0,this.apiEvents.length)}},{key:"version",value:function(){return"3.1.0"}}]),e}();return function(){var e=arguments.length>0&&void 0!==arguments[0]?arguments[0]:{},t=new te(e);return t.init(),t}}));
    /Applications/quarto/share/formats/revealjs/themes/serif.scss:11:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/revealjs/themes/serif.scss:31:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/darkly.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/darkly.scss:4:$theme: "darkly" !default;
    /Applications/quarto/share/formats/html/bootstrap/themes/darkly.scss:188:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/bslib/components/scss/accordion.scss:3:    @include bootstrap-heading($h2-font-size);
    /Applications/quarto/share/formats/html/templates/title-block.scss:1:/*-- scss: functions --*/
    /Applications/quarto/share/formats/html/templates/title-block.scss:32:/*-- scss:variables --*/
    /Applications/quarto/share/formats/html/templates/title-block.scss:37:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/cosmo.scss:1:/*-- scss:defaults --*/
    /Applications/quarto/share/formats/html/bootstrap/themes/cosmo.scss:4:$theme: "cosmo" !default;
    /Applications/quarto/share/formats/html/bootstrap/themes/cosmo.scss:73:/*-- scss:rules --*/
    /Applications/quarto/share/formats/html/axe/axe-check.js:437:    new bootstrap.Offcanvas(offcanvas).show();
    /Applications/quarto/share/formats/html/bootstrap/themes/superhero.scss:1:/*-- scss:defaults --*/
    ✓ • 0ms

## Activity

    $ git status --short; sed -n '1,190p' ps3_part_a.qmd
    ?? ps3_part_a.qmd
    ?? ps3_part_b.qmd
    ---
    title: "Reproducibility check: Joel et al. (2014), Study 1"
    author: "[Your name]"
    date: today
    format:
      html:
        toc: true
    execute:
      echo: true
      warning: false
      message: false
    ---
    
    ## Article
    
    - Citation and DOI: Joel, S., Teper, R., & MacDonald, G. (2014). “People Overestimate Their Willingness to Reject Potential Romantic Partners by Overlooking Their Concern for Other People.” *Psychological Science, 25*(12). [https://doi.org/10.1177/0956797614552828](https://doi.org/10.1177/0956797614552828).
    - Data/materials repository URL: None supplied in the Choice 1 folder. The local materials used here are `ps3/Group A/Choice 1/article.pdf`, `reproducibilityReport.Rmd`, and `data/Empathy Gap Study 1 data.sav`.
    - Part A (known case) or Part B (a classmate's project paper): **Part A, Group A, Choice 1, Study 1.**
    - Part B only: Not applicable.
    
    ## Target outcomes
    
    The targets below were specified in `ps3/Group A/Choice 1/reproducibilityReport.Rmd` before the data were inspected. They are quoted there from the article's Study 1 results.
    
    | # | Target outcome (quoted) | Paper value(s) |
    |---|---|---|
    | 1 | “Only 10 of the 61 participants in the hypothetical condition chose to exchange contact information with the unattractive potential date (16%).” | 10/61; 16% |
    | 2 | “In contrast, 26 of the 71 participants in the real condition chose to exchange contact information (37%).” | 26/71; 37% |
    | 3 | “A chi-square test of independence indicated that participants were significantly less likely to reject the unattractive potential date in the real condition compared with the hypothetical condition, X^2(1, N = 132) = 6.77, p = .009.” | χ²(1, N = 132) = 6.77; p = .009 |
    
    ## Materials inventory
    
    | Item | Available? | Notes |
    |---|---|---|
    | Raw data | No separate unprocessed file | The folder contains an author-provided Study 1 SPSS analysis dataset with 132 rows. The report describes 150 recruited students, but the supplied file does not contain the other 18 rows. |
    | Processed data | Yes | `data/Empathy Gap Study 1 data.sav`; Study 2 data are also present but not used. |
    | Codebook / variable descriptions | Partial | SPSS variable and value labels identify `condition` and `exchangeinfo`; no separate codebook is supplied. |
    | Analysis code | Partial | `reproducibilityReport.Rmd` gives the load command and specifies `chisq.test(..., correct = FALSE)`, but leaves the analysis chunks empty. |
    | Preregistration | Not supplied | No preregistration file is in the folder. |
    
    ## Reproduction
    
    All analysis code is shown below. The SPSS value labels establish the coding: `condition` is 0 = hypothetical and 1 = real; `exchangeinfo` is 1 = yes and 2 = no. The analysis uses the 132 rows in the supplied Study 1 dataset, with no additional exclusions.
    
    ```{r}
    #| label: setup
    library(haven)
    library(knitr)
    ```
    
    ```{r}
    #| label: load
    study1 <- read_sav("ps3/Group A/Choice 1/data/Empathy Gap Study 1 data.sav")
    
    # Display the source labels so the recoding is auditable.
    attr(study1$condition, "labels")
    attr(study1$exchangeinfo, "labels")
    ```
    
    ```{r}
    #| label: preprocess
    stopifnot(
      identical(unname(attr(study1$condition, "labels")), c(0, 1)),
      identical(names(attr(study1$condition, "labels")), c("hypothetical", "real")),
      identical(unname(attr(study1$exchangeinfo, "labels")), c(1, 2)),
      identical(names(attr(study1$exchangeinfo, "labels")), c("yes", "no"))
    )
    
    analysis_data <- data.frame(
      condition = factor(as.numeric(study1$condition),
                         levels = c(0, 1), labels = c("Hypothetical", "Real")),
      exchange = factor(as.numeric(study1$exchangeinfo),
                        levels = c(1, 2), labels = c("Yes", "No"))
    )
    stopifnot(nrow(analysis_data) == 132L, !anyNA(analysis_data))
    ```
    
    ```{r}
    #| label: analysis
    counts <- table(analysis_data$condition, analysis_data$exchange)
    print(counts)
    
    descriptives <- data.frame(
      Condition = rownames(counts),
      Exchanged = as.integer(counts[, "Yes"]),
      Total = as.integer(rowSums(counts)),
      Percent = round(100 * counts[, "Yes"] / rowSums(counts), 2)
    )
    kable(descriptives, row.names = FALSE,
          caption = "Study 1 contact-information exchange")
    
    # Pearson's chi-square test, without Yates' continuity correction as instructed.
    test <- chisq.test(counts, correct = FALSE)
    test
    
    results <- data.frame(
      Chi_square = unname(test$statistic),
      df = unname(test$parameter),
      N = sum(counts),
      p = test$p.value
    )
    kable(results, digits = c(4, 0, 0, 6),
          caption = "Pearson chi-square test of condition by exchange decision")
    ```
    
    **Agent's reproduction claim:** All three specified outcomes were reproduced. The hypothetical condition has 10 of 61 exchanging contact information (16.39%, reported as 16%); the real condition has 26 of 71 (36.62%, reported as 37%). The Pearson test gives χ²(1, N = 132) = 6.7674, p = 0.009284, which round to χ² = 6.77 and p = .009. The complementary rejection counts are 51/61 and 45/71, consistent with the stated direction.
    
    ## Checker's verdict
    
    
    ## Time
    
    - Your time (hours):
    - Agent wall-clock time (hours):
    - Stopped at the 4-hour cap? What remained:
    
    ## Assessment
    
    The agent reproduced the primary Study 1 result from the supplied analysis dataset. The main source of possible ambiguity was the numeric coding of the two variables; the SPSS value labels resolved it. A separate codebook and complete original analysis script would have made the procedure easier to check. The supplied file contains 132 analyzed rows, so this report does not independently verify how the original 150 students were reduced to that sample.
    
    ## AI documentation
    
    - Agent and interface: Codex, accessed via API.
    - Model and version, if the tool reports it: GPT-6; no more specific version was reported in this session.
    - Context given to the agent: The user named `ps3/Group A/Choice 1/reproducibilityReport.Rmd`, the materials in that folder, and `ps3_check_template.qmd`.
    - Number of times you intervened, and the most important intervention: To be completed by the checker.
    - Transcript: To be added by the checker if an export is available. Initial user prompt: “Reproduce the target outcomes specified in ps3/Group A/Choice 1/reproducibilityReport.Rmd, using the materials in that folder. Use ps3_check_template.qmd as the report template and save the report as ps3_part_a.qmd. Keep all analysis code visible and state which outcomes you successfully reproduced. Leave the Checker's verdict section blank for me to complete.”
    ✓ • 59ms

## Activity

    $ quarto --version; quarto render --help | rg -n 'minimal|theme|output-dir|output' | head -40
    1.10.18
    12:  -t, --to                            - Specify output format(s).
    13:  -o, --output                        - Write output to FILE (use '--output -' for stdout).
    14:  --output-dir                        - Write output to DIR (path is input/project relative)
    16:  --site-url                          - Override site-url for website or book output
    23:  --execute-debug                     - Show debug output when executing computations.
    25:  --cache                             - Cache execution output (--no-cache to prevent cache).
    27:  --no-clean                          - Do not clean project output-dir prior to render
    33:  --quiet                             - Suppress console output.
    52:  Render to Stdout:   quarto render document.qmd --output -
    ✓ • 663ms

## Activity

    $ quarto render ps3_part_a.qmd --to html -M minimal:true --output ps3_part_a_check.html --output-dir /private/tmp
    During startup - Warning messages:
    1: Setting LC_CTYPE failed, using "C"
    2: Setting LC_COLLATE failed, using "C"
    3: Setting LC_TIME failed, using "C"
    4: Setting LC_MESSAGES failed, using "C"
    5: Setting LC_MONETARY failed, using "C"
    
    
    processing file: ps3_part_a.qmd
    1/9
    2/9 [setup]
    3/9
    4/9 [load]
    5/9
    6/9 [preprocess]
    7/9
    8/9 [analysis]
    9/9
    output file: ps3_part_a.knit.md
    
    ERROR: Theme file compilation failed:
    
    ../../runtime/vm/cpuinfo_macos.cc: 42: error: unreachable code
    version=3.12.2 (stable) (Tue Jun 9 01:11:39 2026 -0700) on "macos_x64"
    pid=14512, thread=259, isolate_group=(nil)(0x0), isolate=(nil)(0x0)
    os=macos, arch=x64, comp=no, sim=no
    isolate_instructions=0, vm_instructions=0
    fp=7ff7b4e3c730, sp=7ff7b4e3c710, pc=10b332e66
      pc 0x000000010b332e66 fp 0x00007ff7b4e3c730 Dart_IsolateRunnableLatencyMetric+0x23c386
      pc 0x000000010b0efd42 fp 0x00007ff7b4e3c810 Dart_IsPrecompiledRuntime+0xa7a2
      pc 0x000000010b2bcedd fp 0x00007ff7b4e3cc50 Dart_IsolateRunnableLatencyMetric+0x1c63fd
      pc 0x000000010b2bcd2d fp 0x00007ff7b4e3cc60 Dart_IsolateRunnableLatencyMetric+0x1c624d
      pc 0x000000010b2bd250 fp 0x00007ff7b4e3d2b0 Dart_IsolateRunnableLatencyMetric+0x1c6770
      pc 0x000000010b2bd6fb fp 0x00007ff7b4e3d2c0 Dart_IsolateRunnableLatencyMetric+0x1c6c1b
      pc 0x000000010b0ec4f9 fp 0x00007ff7b4e3d800 Dart_IsPrecompiledRuntime+0x6f59
      pc 0x000000010b0eb6bd fp 0x00007ff7b4e3d820 Dart_IsPrecompiledRuntime+0x611d
      pc 0x00007ff816a33345 fp 0x00007ff7b4e3da40 start+0x775
    
    Stack trace:
        at dartCommand (file:///Applications/quarto/bin/quarto.js:79972:11)
        at async dartCompile (file:///Applications/quarto/bin/quarto.js:79926:3)
        at async file:///Applications/quarto/bin/quarto.js:87663:9
        at async SassCache.setFromHash (file:///Applications/quarto/bin/quarto.js:80089:11)
        at async compileSass (file:///Applications/quarto/bin/quarto.js:87474:19)
        at async resolveSassBundles (file:///Applications/quarto/bin/quarto.js:125332:17)
        at async resolveExtras (file:///Applications/quarto/bin/quarto.js:129987:14)
        at async runPandoc (file:///Applications/quarto/bin/quarto.js:129415:20)
        at async renderPandoc (file:///Applications/quarto/bin/quarto.js:131107:24)
        at async Object.onRender (file:///Applications/quarto/bin/quarto.js:137191:30)
        at async renderFileInternal (file:///Applications/quarto/bin/quarto.js:137168:9)
        at async renderFiles (file:///Applications/quarto/bin/quarto.js:136884:9)
        at async renderProject (file:///Applications/quarto/bin/quarto.js:137468:23)
        at async _Command.actionHandler (file:///Applications/quarto/bin/quarto.js:142798:24)
        at async _Command.execute (file:///Applications/quarto/bin/quarto.js:102189:7)
        at async _Command.parseCommand (file:///Applications/quarto/bin/quarto.js:102066:14)
        at async quarto4 (file:///Applications/quarto/bin/quarto.js:188195:5)
        at async file:///Applications/quarto/bin/quarto.js:188224:5
        at async file:///Applications/quarto/bin/quarto.js:188078:14
        at async mainRunner (file:///Applications/quarto/bin/quarto.js:188080:5)
        at async file:///Applications/quarto/bin/quarto.js:188217:3
    ✗ (1) • 3.06s

## Activity

    $ sed -n '79895,79980p' /Applications/quarto/bin/quarto.js; sed -n '87445,87515p' /Applications/quarto/bin/quarto.js
      }
      const brand = format14.render.brand;
      if (brand && brand.dark) {
        return false;
      }
      return void 0;
    }
    var init_format_html_info = __esm({
      "format/html/format-html-info.ts"() {
        init_constants6();
        init_format5();
      }
    });
    
    // core/dart-sass.ts
    async function dartCompile(input, outputFilePath, temp, loadPaths, compressed) {
      const inputFilePath = temp.createFile({ suffix: ".scss" });
      Deno.writeTextFileSync(inputFilePath, input);
      const args = [
        inputFilePath,
        outputFilePath,
        "--style",
        compressed ? "compressed" : "expanded",
        "--quiet"
        // Remove this flag to get depedency warnings from SASS
      ];
      if (loadPaths) {
        loadPaths.forEach((loadPath) => {
          args.push(`--load-path=${loadPath}`);
        });
      }
      await dartCommand(args);
      return outputFilePath;
    }
    function resolveSassCommand(options) {
      const installDir4 = options?.installDir;
      if (installDir4 == null) {
        const dartOverrideCmd = Deno.env.get("QUARTO_DART_SASS");
        if (dartOverrideCmd) {
          if (!existsSync2(dartOverrideCmd)) {
            warnOnce(
              `Specified QUARTO_DART_SASS does not exist, using built in dart sass.`
            );
          } else {
            return { cmd: dartOverrideCmd, baseArgs: [] };
          }
        }
      }
      const sassDir = installDir4 ?? architectureToolsPath("dart-sass");
      if (isWindows4) {
        return {
          cmd: join4(sassDir, "src", "dart.exe"),
          baseArgs: [join4(sassDir, "src", "sass.snapshot")]
        };
      }
      return { cmd: join4(sassDir, "sass"), baseArgs: [] };
    }
    async function dartCommand(args, options) {
      const { cmd, baseArgs } = resolveSassCommand(options);
      const result2 = await execProcess({
        cmd,
        args: [...baseArgs, ...args],
        stdout: "piped",
        stderr: "piped"
      });
      if (result2.success) {
        if (result2.stderr) {
          info(result2.stderr);
        }
        return result2.stdout;
      } else {
        debug(`[DART cmd]    : ${cmd}`);
        debug(`[DART args]   : ${[...baseArgs, ...args].join(" ")}`);
        debug(`[DART stdout] : ${result2.stdout}`);
        debug(`[DART stderr] : ${result2.stderr}`);
        const errLines = lines(result2.stderr || "");
        const errMsg = errLines.slice(0, errLines.length - 2).join("\n");
        throw new Error("Theme file compilation failed:\n\n" + errMsg);
      }
    }
    var init_dart_sass = __esm({
      "core/dart-sass.ts"() {
        init_path();
        init_resources2();
        init_process();
        init_text2();
        userFunctions,
        '// quarto-scss-analysis-annotation { "origin": "Defaults from user-defined SCSS" }',
        userDefaults,
        `// quarto-scss-analysis-annotation { "origin": "Defaults from Quarto's SCSS" }`,
        ...quartoDefaults2.reverse(),
        '// quarto-scss-analysis-annotation { "origin": "Defaults from the format SCSS" }',
        ...frameworkDefaults.reverse(),
        `// quarto-scss-analysis-annotation { "origin": "'mixins' section from format" }`,
        ...frameworkMixins,
        `// quarto-scss-analysis-annotation { "origin": "'mixins' section from Quarto" }`,
        ...quartoMixins,
        `// quarto-scss-analysis-annotation { "origin": "'mixins' section from user-defined SCSS" }`,
        userMixins,
        `// quarto-scss-analysis-annotation { "origin": "'rules' section from format" }`,
        ...frameworkRules,
        `// quarto-scss-analysis-annotation { "origin": "'rules' section from Quarto" }`,
        ...quartoRules2,
        `// quarto-scss-analysis-annotation { "origin": "'rules' section from user-defined SCSS" }`,
        userRules,
        '// quarto-scss-analysis-annotation { "origin": null }'
      ].join("\n\n");
      const saveScssPrefix = Deno.env.get("QUARTO_SAVE_SCSS");
      if (saveScssPrefix) {
        const counterValue = counter++;
        Deno.writeTextFileSync(
          `${saveScssPrefix}-${counterValue}.scss`,
          scssInput
        );
      }
      const result2 = await compileWithCache(
        scssInput,
        loadPaths,
        project,
        {
          compressed: minified,
          cacheIdentifier: await md5HashBytes(new TextEncoder().encode(scssInput)),
          addVarsBlock: true
        }
      );
      if (saveScssPrefix) {
        const partialOutput = Deno.readTextFileSync(result2);
        const scssToWrite = [scssInput];
        const internalVars = Array.from(
          partialOutput.matchAll(/(--quarto-scss-export-[^;}]+;?)/g)
        ).map((m4) => m4[0]);
        const annotation = {
          "css-vars": internalVars
        };
        scssToWrite.push(
          `// quarto-scss-analysis-annotation ${JSON.stringify(annotation)}`
        );
        scssInput = scssToWrite.join("\n");
        Deno.writeTextFileSync(
          `${saveScssPrefix}-${counter - 1}.scss`,
          scssInput
        );
      }
      return result2;
    }
    function mergeLayers(...layers) {
      const themeUses = [];
      const themeDefaults = [];
      const themeRules = [];
      const themeFunctions = [];
      const themeMixins = [];
      layers.forEach((theme) => {
        if (theme.uses) {
          themeUses.push(theme.uses);
        }
        if (theme.defaults) {
          themeDefaults.push(theme.defaults);
    ✓ • 0ms

## Activity

    $ uname -m; command -v sass; find /Applications/quarto -type f -name 'sass' -maxdepth 7 | head -15; git status --short
    x86_64
    /Applications/quarto/bin/tools/aarch64/dart-sass/sass
    /Applications/quarto/bin/tools/x86_64/dart-sass/sass
     M .gitignore
    ?? ps3_part_a.qmd
    ?? ps3_part_b.qmd
    ✓ • 127ms

## Activity

    $ rg -n 'QUARTO_DART_SASS|sass-embedded|dart-sass' /Applications/quarto/bin/quarto.js | head -35
    79909:// core/dart-sass.ts
    79932:    const dartOverrideCmd = Deno.env.get("QUARTO_DART_SASS");
    79936:          `Specified QUARTO_DART_SASS does not exist, using built in dart sass.`
    79943:  const sassDir = installDir4 ?? architectureToolsPath("dart-sass");
    79976:  "core/dart-sass.ts"() {
    ✓ • 0ms

## Activity

    $ file /Applications/quarto/bin/tools/x86_64/dart-sass/sass /Applications/quarto/bin/tools/aarch64/dart-sass/sass; /Applications/quarto/bin/tools/x86_64/dart-sass/sass --version
    /Applications/quarto/bin/tools/x86_64/dart-sass/sass:  POSIX shell script text executable, ASCII text
    /Applications/quarto/bin/tools/aarch64/dart-sass/sass: POSIX shell script text executable, ASCII text
    ../../runtime/vm/cpuinfo_macos.cc: 42: error: unreachable code
    version=3.12.2 (stable) (Tue Jun 9 01:11:39 2026 -0700) on "macos_x64"
    pid=14531, thread=259, isolate_group=(nil)(0x0), isolate=(nil)(0x0)
    os=macos, arch=x64, comp=no, sim=no
    isolate_instructions=0, vm_instructions=0
    fp=7ff7b8937bb0, sp=7ff7b8937b90, pc=107837e66
      pc 0x0000000107837e66 fp 0x00007ff7b8937bb0 Dart_IsolateRunnableLatencyMetric+0x23c386
      pc 0x00000001075f4d42 fp 0x00007ff7b8937c90 Dart_IsPrecompiledRuntime+0xa7a2
      pc 0x00000001077c1edd fp 0x00007ff7b89380d0 Dart_IsolateRunnableLatencyMetric+0x1c63fd
      pc 0x00000001077c1d2d fp 0x00007ff7b89380e0 Dart_IsolateRunnableLatencyMetric+0x1c624d
      pc 0x00000001077c2250 fp 0x00007ff7b8938730 Dart_IsolateRunnableLatencyMetric+0x1c6770
      pc 0x00000001077c26fb fp 0x00007ff7b8938740 Dart_IsolateRunnableLatencyMetric+0x1c6c1b
      pc 0x00000001075f14f9 fp 0x00007ff7b8938c80 Dart_IsPrecompiledRuntime+0x6f59
      pc 0x00000001075f06bd fp 0x00007ff7b8938ca0 Dart_IsPrecompiledRuntime+0x611d
      pc 0x00007ff816a33345 fp 0x00007ff7b8938ec0 start+0x775
    -- End of DumpStackTrace
    ✗ (134) • 0ms

## Activity

    $ node -e 'for (const x of ["sass","sass-embedded"]) {try {console.log(x,require.resolve(x))} catch(e) {console.log(x,"absent")}}'; ls /usr/local/lib/node_modules 2>/dev/null | head -30; ls /opt/homebrew/bin/sass 2>/dev/null
    sass absent
    sass-embedded absent
    corepack
    npm
    ✗ (1) • 67ms
