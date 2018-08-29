# Knowbase: Your personal knowledge database.

## syntax

- Tags are marked with `@`
- Keep the whole thing in a single line for now.

## usage

The database is just a text file, so you can use your favorite text editor and/or
unix tools like `cat` and `grep` and so forth. Below, is my setup which may be
helpful to you, specially as your databases grow in size and become harder to
search.

- Download [fzf](https://github.com/junegunn/fzf). This is an awesome tool that really
  takes things to the next level in terms of searching your databases.
- To search your database when you have no clue what you are looking for or just to
  explore, do `cat <yourdatabasename.kb> | fzf`. This is the most flexible way to
  look through your kbits, but it can become inefficient as your databases grow.
- To search your database when you know the tag(s) you are looking for, you can
  do `cat <yourdatabasename.kb> | fzf -e`. the `-e` allows for exact matches,
  limiting the fuzziness of the seach. Note that while this will match exact
  words, the order is still fuzzy when searching for multiple words. So for
  instance searching for `@tag1 @tag2` will bring up any lines containing those
  tags in any order. This is awesome as you dont have to think about the order
  of your tags when you are adding kbits.
- If your database is growing very large, you can limit it by filtering on a
  word or tag with `cat <yourdatabasename.kb> | grep wordOrTag | fzf`

