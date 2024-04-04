const readline = require('readline');

function add(a, b) {
    return a + b;
}

function subtract(a, b) {
    return a - b;
}

function multi(a, b) {
    return a * b;
}

function division(a, b) {
    if (b !== 0) {
        return a / b;
    } else {
        console.log("Error: Division by zero");
        return NaN;
    }
}

const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

function main() {
    rl.question("Enter your choice\n" +
        "Choose 1 for addition\n" +
        "Choose 2 for subtraction\n" +
        "Choose 3 for multiplication\n" +
        "Choose 4 for division\n" +
        "Choose 5 to exit\n", (choice) => {
            switch (parseInt(choice)) {
                case 1:
                    rl.question("Enter the value of a: ", (a) => {
                        rl.question("Enter the value of b: ", (b) => {
                            console.log("Result: " + add(parseInt(a), parseInt(b)));
                            main();
                        });
                    });
                    break;
                case 2:
                    rl.question("Enter the value of a: ", (a) => {
                        rl.question("Enter the value of b: ", (b) => {
                            console.log("Result: " + subtract(parseInt(a), parseInt(b)));
                            main();
                        });
                    });
                    break;
                case 3:
                    rl.question("Enter the value of a: ", (a) => {
                        rl.question("Enter the value of b: ", (b) => {
                            console.log("Result: " + multi(parseInt(a), parseInt(b)));
                            main();
                        });
                    });
                    break;
                case 4:
                    rl.question("Enter the value of a: ", (a) => {
                        rl.question("Enter the value of b: ", (b) => {
                            console.log("Result: " + division(parseInt(a), parseInt(b)).toFixed(2));
                            main();
                        });
                    });
                    break;
                case 5:
                    console.log("Exiting program...");
                    rl.close();
                    break;
                default:
                    console.log("Invalid choice");
                    main();
            }
    });
}

main();
# calculator1
