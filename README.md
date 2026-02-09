# Rock, Paper, Scissors (Javascript)
## Description
This project utilizes Javascript to play a game of Rock, Paper, Scissors against a computer. I created this project to test out how a game would function using only Javascript. I learned that it is possible to make a game as simple as this, and will see if I can utilize Javascript in the future to make something more complex or dynamic for a website.
## Usage
 Click the link below to test it out.
[# seblanderos.github.io](https://seblanderos.github.io/)
<script>
let wins = 0;
let ties = 0;
let losses = 0;

alert("Welcome to Rock, Paper, Scissors!");

while (true) {
    let userInput = prompt("Enter R for Rock, P for Paper, or S for Scissors:").toUpperCase().trim();
    
    if (userInput === null) {
        break;
    }
    
    if (!['R', 'P', 'S'].includes(userInput)) {
        alert("Invalid input! Please enter only R, P, or S.");
        continue;
    }
    
    const choices = ['R', 'P', 'S'];
    const computerChoice = choices[Math.floor(Math.random() * 3)];
    
    let resultMessage;
    if (userInput === computerChoice) {
        ties++;
        resultMessage = "It's a tie!";
    } else if (
        (userInput === 'R' && computerChoice === 'S') ||
        (userInput === 'P' && computerChoice === 'R') ||
        (userInput === 'S' && computerChoice === 'P')
    ) {
        wins++;
        resultMessage = "You win!";
    } else {
        losses++;
        resultMessage = "Computer wins!";
    }
    
    alert(
        `You chose: ${userInput}\nComputer chose: ${computerChoice}\n\n${resultMessage}\n\n` +
        `Wins: ${wins} | Ties: ${ties} | Losses: ${losses}`
    );
    
    if (!confirm("Play again?")) {
        break;
    }
}

alert(`Game Over!\nFinal Score:\nWins: ${wins} | Ties: ${ties} | Losses: ${losses}`);
</script>
