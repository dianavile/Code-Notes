# Markdown- [Markdown Cheatsheet](#2-GitHub-markdown)
_Source: GitHub Hacknight - Woman Who Code_

### Table Of Contents:
## 1. GitHub Markdown 
- GitHub uses its own version of the Markdown syntax. 
- It provides an _additional set of usefull features_, that make it easier to work with content on GitHub.com:

__GOALS:__
- a. __USERNAME @MENTIONS__
- b. __ISSUE REFERENCES__ 
- c. __TASK LISTS__ 
- d. __FENCED CODE BLOCKS__ 
- e. __TABLES__ 
- f. __EMOJI__ 

## a. USERNAME @MENTIONS 
- Type a @ symbol followe by a username to notify the person to view the comment.
- This is called an "@mention", as you are mentioning an `individual`.
- You can also "@mention" `teams` within an _organization_.

## b. ISSUE REFERENCES 
Any number refering to an `Issue` or `Pull Request` is automatically converted into a link:
- #1
- defunkt#1
- defunkt/github-flavored-markdown#1

## c. TASK LISTS 
- [x] @mentions, #refs, [links](),]]formatting]], and <del>tags</del> supported.
- [x] list syntax required (any unordered list or ordered list supported).
- [x] this is a complete item.
- [] this is an incomplete item.

## d. FENCED CODE BLOCKS
- You can create a code block with ` ``` `to create a clde block without the leading spaces.
```
javascript
function test(){
console.log("look ma`,  no spaces");
}
```
- Add an optional language identifier and your code with get syntax highlighting.
function test (){
console.log("look ma`, no spaces");
}

## e. TABLES
In GitHub you can create a table by 
- assembling a list of words 
- divide them with hyphens (-) for first row 
- separate each column with a pipe `I`
```
First Header     I Second Header
--------------- I -------------
Content cell1   I Content cell2
Content column2 I Content column2
```

## f. EMOJI
GitHub supports emoji!
:+1: :sparkles: :camel: :tada:
:rocket: :metal: :octocat:
See all [available & supported emoji](http://www.emoji-cheat-sheet.com)
