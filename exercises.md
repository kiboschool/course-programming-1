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
pushd .exercises
while read -r line; do
  project=`echo $line | cut -d ':' -f 1`
  mkdir -p $project
  pushd $project
  url=`echo $line | cut -d ':' -f 2,3`
  git clone $url .
  popd
done < ../exercise-map.txt
popd
```

## What you get:

After you run the above, you should have a directory `.exercises` so that `tree
-L 2 .exercises` shows the following:

(updated 9/2/22; good to keep this up to date with the actual exercises)

```
.
├── 01-basics-and-datatypes
│   ├── ac-load-estimator
│   ├── body-mass-index
│   ├── mad-libs-project
│   └── usd-to-naira-conversion
├── 02-conditionals
│   ├── exam-results
│   ├── money-for-books
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
│   ├── squad-info-chat-bot-project
│   └── squad-mates
├── 05-functions
│   ├── add-list-numbers
│   ├── greet-person-function
│   ├── py-distance-traveled
│   ├── quick-draw
│   └── smallest-item-in-a-list
├── 06-organizing-code
│   ├── circle-area
│   ├── data-processor
│   ├── date-format
│   ├── message-encode-decode
│   └── unit-conversion-functions
├── 07-files
│   ├── binary-scorekeeping
│   ├── count-file-lines
│   ├── file-checks
│   ├── read-binary-file
│   ├── read-file-into-array
│   └── replace-char-in-file
├── 08-data-structures
│   ├── log-analyzer-project
│   ├── phone-book
│   ├── row-sum
│   └── word-frequency
├── 09-libraries
│   ├── json-parsing
│   └── requests-exercise
└── 10-review
    └── robot-translator
```
