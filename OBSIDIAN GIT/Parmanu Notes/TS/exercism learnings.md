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

