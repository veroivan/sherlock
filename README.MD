# Sherlock 

Goal of this project is to provide an easy way to play [Sherlock Holmes Consultant Detective](https://boardgamegeek.com/boardgame/2511/sherlock-holmes-consulting-detective-thames-murder) fan cases.
It's done with Jekyll, so it's just a pretty bare bones static sites, it doesn't provide any advanced features like leads tracking, there's still a lot of room for improvement.

Here's the link to the published site: https://veroivan.github.io/sherlock/

## How to create new cases
Creating a new case is easy but, as of now, requires a bit of manual work. Look at `accademico_assassinato` to see a working example.
Under `_cases` folder create a new folder named after the case, and under that create a markdown file for each valid address, with this naming convention: `ADDRESS.md` (e.g. `21SE.md`).
Each lead must contain a front matter in this format:
```
---
layout: case
type: lead
title: 21 SE (it's the title you want to see above your lead text)
language: it (this is for when i'll add multi language support)
case_name: accademico_assassinato (must be the same name you gave to the folder case)
address: 21SE (must be the same of the file name)
---
```
Having done that you can just paste your lead text, and if you need to add image you can just include it like this:
`![]({{site.baseurl}}/assets/images/accademico_assassinato/22SO.jpg)`
Images go under `/assets/images/CASE_NAME/` and a good naming convention would be to name them the same as the address they go under to avoid creating too much entropy.

Besides addresses you need to create 4 other files:
- `intro.md`:
    That's the case introduction text, it has a few extra variables in the front matter:
    ```
        case_date: 18 Marzo 1886    
        author: AUTHOR_NAME (remember to credit case authors!)
        type: intro
    ```
- `questions.md`:
    Case questions, file contains no text in itself, the questions are listed in front matter variables like this:
    ```
        type: questions
        questions:
            first_series: 
                - Who's the killer?
                - What's the motive?
                - and so on, and so on
            second_series:
                - another interesting question
    ```
- `answers.md`:
    Same format as questions
- `solution.md`:
    Case solution text, similar to every other lead text, but with `type: solution`
    
## Development and deploy
New features must be done on feature branches, then merged to `master`. 
Deploy is triggered when a branch is merged on `gh-pages`. DO NOT merge branches other than `master` on `gh-pages`

## TODO list
- Add London Directory (yes, this is pretty important)
- Add multi language support (or at least a way to filter by language)
- General graphic improvements
- Find a way to keep track of followed leads (not sure if this can be done with Jekyll)
- Find a way to add new cases with less manual work, even some scripts to parse a lot of leads creating the corresponding files would be nice
- Add cases!

## Credits
This project in no way can substite the original games, so go buy them!

Fan case authors get credited in intro files of each case.

Site it built using [Jekyll](https://jekyllrb.com/) using [Hitchens](https://github.com/patdryburgh/hitchens) as base theme.

All resources used come from [here](https://boardgamegeek.com/filepage/124589/custom-mistery-pack) and [here](https://www.spacecowboys.fr/the-irregulars-of-baker-street)