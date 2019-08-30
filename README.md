# PhoneticSpeller
Instead of writing out words with just letters, you have to sound out the spelling of each letter


## Example usage 
type in what you would write as the phonetic spelling of an English letter (be for b for example), 
a character will be produced that tries to match to the character you were trying to spell

## How it works
There's an existing table of mappings between letters and potential phonetic spellings. If the user input
matches an existing mapping then that corresponding letter is returned.

If there's no match, we iterate through all the existing phonetic spellings and compare the user input to each spelling.
An ASCII difference is recorded by comparing the difference between the ASCII values character-by-character.
These differences are recorded in a new table. We also check for the percentage of common characters between the spellings
and multiply our ASCII difference by the inverse of that and the spelling with the minimum difference is expected to correspond
to the correct letter.

### Formula
diff = ASCII Diff * (1-(num of common characters/total characters)

## TODO
Accept space separated input so entire phrases can be produced
Make it pretty
Clean up code

## Notes
The algorithm can be skewed based it on input length it seems (there may be a scenario where it matches to a letter because
the length of the input may have the formula favor another letter). Quickly put together however it seems to be fairly accurate
(no quantifiable results however)

I personally can't find a useful application for this but maybe someone will in which case feel free to use the code.
Also can/should be written utilizing better Javascript style coding
