**`[...strand]`**: This uses the **spread syntax** to convert the `strand` string into an array of individual characters. For example, if `strand` is "GCTA", `[...strand]` will become `['G', 'C', 'T', 'A']`. This is a common and concise way to iterate over string characters

**`.forEach((char, i) => { ... });`**: This is an **array method** that iterates over each element in the `chars` array (which are the individual DNA characters).

- `(char, i)`: This is an **arrow function** that will be executed for each character.
    - `char`: Represents the current character being processed (e.g., 'G', 'C', 'T', 'A').
    - `i`: Represents the index of the current character (though `i` is not used in this specific code).
### Space age prob. learned switch case. it handles problem with soft error handling:
const secondsToEarthYears = (seconds: number): number => {
    return seconds / 31557600;
}

export const age = (planet: string, seconds: number): number => {
    switch(planet) {
        case 'mercury':
            return parseFloat(
              (secondsToEarthYears(seconds) / 0.2408467).toFixed(2)
            );
        case 'venus':
            return parseFloat(
              (secondsToEarthYears(seconds) / 0.61519726).toFixed(2)
            );
        case 'earth':
            return parseFloat(
              (secondsToEarthYears(seconds)).toFixed(2)
            );
        case 'mars':
            return parseFloat(
              (secondsToEarthYears(seconds) / 1.8808158).toFixed(2)
            );
        case 'jupiter':
            return parseFloat(
              (secondsToEarthYears(seconds) / 11.862615).toFixed(2)
            );
        case 'saturn':
            return parseFloat(
              (secondsToEarthYears(seconds) / 29.447498).toFixed(2)
            );
        case 'uranus':
            return parseFloat(
              (secondsToEarthYears(seconds) / 84.016846).toFixed(2)
            );
        case 'neptune':
            return parseFloat(
              (secondsToEarthYears(seconds) / 164.79132).toFixed(2)
            );
        default:
            return 0;
    }
}
### amazing code d&d char:


export class DnDCharacter {
  readonly strength = DnDCharacter.generateAbilityScore()
  readonly dexterity = DnDCharacter.generateAbilityScore()
  readonly constitution = DnDCharacter.generateAbilityScore()
  readonly intelligence = DnDCharacter.generateAbilityScore()
  readonly wisdom = DnDCharacter.generateAbilityScore()
  readonly charisma = DnDCharacter.generateAbilityScore()
  readonly hitpoints = 10 + DnDCharacter.getModifierFor(this.constitution)

  public static generateAbilityScore(): number {
    let rolls: number[] = []
    for (let i = 0; i < 4; i++)
      rolls.push(Math.floor((Math.random() * 6) + 1))

    return rolls.sort().slice(-3).reduce((sum, roll) => sum + roll, 0)
  }

  public static getModifierFor(abilityValue: number): number {
    return Math.floor((abilityValue - 10) / 2)
  }
}
### Set use, store only unique data:
`export function isPangram(sentence: string): boolean {`
  `// 1. Convert the sentence to lowercase to handle case-insensitivity`
  `const lowercasedSentence = sentence.toLowerCase();`

  `// 2. Create a Set to store unique letters found in the sentence.`
  `// Sets automatically handle uniqueness.`
  `const foundLetters = new Set<string>();`

  `// 3. Iterate over each character in the lowercased sentence`
  `for (const char of lowercasedSentence) {`
    `// 4. Check if the character is a letter of the English alphabet`
    `// We can use a regular expression for this: [a-z]`
    `if (char >= 'a' && char <= 'z') { // More efficient than regex for single char`
      `// 5. Add the letter to the Set. If it's already there, Set does nothing.`
      `foundLetters.add(char);`
    `}`
    `// Non-alphabetic characters (spaces, numbers, punctuation) are ignored`
  `}`

  `// 6. A pangram contains all 26 letters of the English alphabet.`
  `// Check if the size of the Set is 26.`
  `return foundLetters.size === 26;`
`}`
### Bob, const fn() and ` /[a-zA-Z]/.test(str);` :



