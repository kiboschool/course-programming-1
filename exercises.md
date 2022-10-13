# Exercises

You can clone all the exercises for this course into an ignored hidden folder called
`.exercises`. All the exercises have their own git repos, so take care not to
accidentally add them to this repository; submodules and nested git projects are
messy.

## Clone everything

Do a little shell-dance to clone each of the exercises (check the map of
exercises, git urls, and where they'll end up with `cat exercise-map.txt`)

```sh
mkdir -p .exercises
while read -r line; do
  project=`echo $line | cut -d ':' -f 1`
  mkdir -p $project
  pushd $project
  url=`echo $line | cut -d ':' -f 2,3`
  git clone $url .
  popd
done < ../exercise-map.txt
```

## Git pull all

To refresh all the exercises

From `.exercises`:

```sh
find . -type d -maxdepth 2 -mindepth 2  |
while read -r project; do
        pushd $project
        echo $project
        git checkout main
        git pull
        popd
done
```

## Update the list of exercises

i.e. if you added or removed an exercise (folder within one of the weeks in
`.exercises`, with a git remote)

from .exercises:

```sh
setopt PUSHDSILENT
find .exercises -type d -maxdepth 2 -mindepth 2  |
while read -r project; do
  pushd $project
  echo -n "$project:"; git remote get-url origin
  popd
done | sort > exercise-map.txt
```

## Add another remote to all the exercises and push

When we create a new github org to run the course, we need to create new repos, 
add them as new remotes, and push each project and exercise to the new repo.

* Edit so that the org name and remote name match the term
* Requires the [Github CLI](https://cli.github.com/)

from `.exercises`:

```sh
find . -type d -maxdepth 2 -mindepth 2  |
while read -r project; do
        pushd $project
        echo $project
        git checkout main
        name=$(echo $project | cut -d '/' -f 3)
        gh repo create "kibo-programming-1-oct-22/$name" --source=. --private --remote=oct-22 --push
        popd
done
```

## Add all the students as members of a team

It's useful to have a team for 'all the students' which you can then add to
other repos to give specific permissions. But... clicking through the 'add team
member' dialog is really bad. Do this instead.

- requires gh and jq
- requires all the students to have joined the gh org (e.g. by accepting a gh
    classroom assignment)
- also adds any other org members to this team, so, be aware
- create the team and org
- update the org name and team name as appropriate

be careful and run this line by line.

```sh
SETOPT interactivecomments
org="kibo-programming-1-oct-22"
team="all-students"
students=$(gh api -X GET /orgs/$org/members | jq -r '.[].login')
echo $students | 
while read -r student; do
  echo "/orgs/$org/teams/$team/memberships/$student"
  # uncomment to actually do the thing
  # gh api -X PUT "/orgs/$org/teams/$team/memberships/$student" -F role='member'
done
```

## For all exercises, push a branch to a given remote

change 'main' and 'oct-22' as appropriate

from `.exercises`:

```sh
find . -type d -maxdepth 2 -mindepth 2  |
while read -r project; do
        pushd $project
        echo $project
        git checkout main
        git push oct-22 main
        popd
done
```

## Fixup a Replit exercise

Given an exercise from replit that's been connected via the Replit github
button, but has files named weird (all under `.lesson` or whatever) because of
Replit being weird, you can fix it like this:

```sh
git rm .breakpoints
git mv .lesson/instructions.md ./README.md
git mv .lesson/* ./
rmdir .lesson
git add .
git restore --staged solution.py
git commit --amend -m "Initial commit"
git push -f
co -b solution
mv solution.py main.py
git add .
git commit -m "add solution"
git push
co main
```

- unconditionally removes replit breakpoints
- assumes there's a solution.py file in .lesson that is the solution
- Does some fairly aggro git pushing, rewriting remote history. Take care.

## Exercise Tree

After you run the above, you should have a directory `.exercises` so that `tree
-L 2 .exercises` shows the following:

(updated 9/13/22; good to keep this up to date with the actual exercises)

```
.exercises
├── 01-basics-and-datatypes
│   ├── ac-load-estimator
│   ├── body-mass-index
│   ├── mad-libs-project
│   └── usd-to-naira-conversion
├── 02-conditionals
│   ├── exam-results
│   ├── money-for-books
│   ├── quick-draw
│   └── rock-paper-scissors-project
├── 03-loops
│   ├── guess-my-number-project
│   ├── print-multiples
│   └── scrabble-word-score
├── 04-lists
│   ├── list-average
│   ├── longest-word
│   ├── roster-change
│   ├── safari-animals
│   └── squad-mates
├── 05-functions
│   ├── add-list-numbers
│   ├── bmi-with-functions
│   ├── circle-area
│   ├── double-list-elements
│   ├── greet-person-function
│   ├── smallest-item-in-a-list
│   └── unit-conversion-functions
├── 06-organizing-code
│   ├── date-format
│   ├── distance-traveled
│   ├── microprocessor-simulation
│   └── random-story-generator
├── 07-files
│   ├── binary-file-info
│   ├── binary-scorekeeping
│   ├── count-file-lines
│   ├── directory-maintainer
│   ├── file-checks
│   └── replace-char-in-file
├── 08-data-structures
│   ├── log-analyzer-project
│   ├── phone-book
│   ├── row-sum
│   └── word-frequency
├── 09-libraries
│   ├── fetching-web-data
│   ├── json-parsing
│   └── message-encode-decode
├── 10-review
│   └── robot-translator
└── projects
    ├── final-project-pop-analysis
    └── midterm-project-team-chatbot
```
