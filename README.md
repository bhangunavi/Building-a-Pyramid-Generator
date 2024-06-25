# Building-a-Pyramid-Generator
This generator will create a pyramid of a specified height, and it will allow for both normal and inverted pyramids based on a boolean flag.
Explanation
Initialization:

const character = "#";: Defines the character used to build the pyramid.
const count = 8;: Specifies the height of the pyramid (number of rows).
const rows = [];: Initializes an empty array to store the rows of the pyramid.
let inverted = true;: A boolean flag to determine whether the pyramid should be inverted or not.
padRow Function:

function padRow(rowNumber, rowCount) { ... }: This function generates a single row of the pyramid.
rowNumber: The current row number being generated.
rowCount: The total number of rows in the pyramid.
return " ".repeat(rowCount - rowNumber) + character.repeat(2 * rowNumber - 1) + " ".repeat(rowCount - rowNumber);:
" ".repeat(rowCount - rowNumber): Adds spaces to the left to center-align the row.
character.repeat(2 * rowNumber - 1): Adds the appropriate number of pyramid characters (#) for the row.
" ".repeat(rowCount - rowNumber): Adds spaces to the right to center-align the row.
Conditional Generation:

if (inverted) { ... } else { ... }: Checks the value of the inverted flag to determine the order of row addition.
for (let i = 1; i <= count; i++) { ... }: A loop that runs from 1 to count to generate each row of the pyramid.
If inverted is true:
rows.unshift(padRow(i, count));: Adds each generated row to the beginning of the rows array, creating an inverted pyramid.
If inverted is false:
rows.push(padRow(i, count));: Adds each generated row to the end of the rows array, creating a normal pyramid.
Building the Result String:

let result = "";: Initializes an empty string to build the final result.
for (const row of rows) { result = result + "\n" + row; }: Concatenates all rows in the rows array into the result string, with newline characters between each row to format the pyramid correctly.
Printing the Result:

console.log(result);: Outputs the final pyramid to the console.
