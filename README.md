# String Similarity in Google Sheets

This Google Apps Script provides a way to find the most similar string to a target string in a list of strings. It makes use of a combination of string similarity and Levenshtein distance measures to find the best match. The script also includes a function to group keywords based on their similarity to a list of ad groups.

## How to Use

1. In your Google Sheets, click on `Extensions > Apps Script`.

2. Copy and paste the entire script code into the Apps Script Editor.

3. Save the project with a suitable name.

4. You can now use the `FINDSIMILARTEXT` and `GROUP_KEYWORD` functions in your Google Sheets.

### FINDSIMILARTEXT Function

Syntax: `FINDSIMILARTEXT(targetPhrase, phraseList, minimumScore, returnType)`

- `targetPhrase`: The string to which you want to find a similar string in the `phraseList`. Can be a single cell reference.
- `phraseList`: The range (only a single column or row) containing the list of strings to compare with the `targetPhrase`. 
- `minimumScore`: Optional. The minimum score for a match to be considered valid. Default is 0.
- `returnType`: Optional. The type of value to return. Can be "text" or "position". If "text", the function returns the most similar string. If "position", the function returns the position of the most similar string in the `phraseList`.

Example: `=FINDSIMILARTEXT(A1, B1:B10, 0.5, "text")`

### GROUP_KEYWORD Function

Syntax: `GROUP_KEYWORD(keyword, adGroups, allKeywords)`

- `keyword`: The keyword to group. Can be a single cell reference.
- `adGroups`: The range (only a single column) containing the list of ad groups.
- `allKeywords`: The range (only a single column) containing the list of all keywords.

This function finds the most similar string in `adGroups` to the `keyword`. If there is no good match in `adGroups`, it tries to find the most similar keyword in `allKeywords`.

Example: `=GROUP_KEYWORD(A1, B1:B10, C1:C100)`

Note: The script assumes a similarity threshold of 0.5 for grouping keywords. You can adjust this value in the Apps Script Editor.

## Contribution

Feel free to fork the project, open a pull request, or submit an issue. Contributions are welcome!

## License

This project is licensed under the terms of the MIT license.
