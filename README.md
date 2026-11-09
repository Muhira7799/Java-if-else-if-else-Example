# Java `if / else if / else` Example

A minimal Java program that demonstrates a chain of `if`, `else if`, and `else` statements by printing a greeting based on the value of a number.

## What It Demonstrates

```java
int i = 25;

if (i < 10) {
    System.out.println("Good morning");
} else if (i < 25) {
    System.out.println("Good afternon");
} else if (i < 20) {
    System.out.println("Good evening");
} else {
    System.out.println("Good bye");
}
```

Java checks the conditions from top to bottom and runs only the **first** block whose condition is true. If none are true, the `else` block runs.

## How It Works

With `i = 25`:

| Check | Result |
|-------|--------|
| `i < 10` | false (25 is not less than 10) |
| `i < 25` | false (25 is not less than 25) |
| `i < 20` | false (25 is not less than 20) |
| `else` | runs |

## Output

```
Good bye
```

## Important: One Branch Can Never Run

The `i < 20` branch (`Good evening`) is unreachable. Any value below 20 is already caught by an earlier condition:

- Values below 10 match `i < 10`
- Values from 10 to 24 match `i < 25`

So `Good evening` can never be printed, whatever the value of `i`.

To make every branch reachable, order the conditions from smallest to largest:

```java
if (i < 10) {
    System.out.println("Good morning");
} else if (i < 20) {
    System.out.println("Good afternoon");
} else if (i < 25) {
    System.out.println("Good evening");
} else {
    System.out.println("Good bye");
}
```

## Results for Different Values of `i`

Using the corrected order above:

| `i` | Output |
|-----|--------|
| 5 | Good morning |
| 15 | Good afternoon |
| 22 | Good evening |
| 25 or more | Good bye |

## Requirements

- Java Development Kit (JDK) 8 or higher

## Getting Started

### Clone the repository

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### Compile

```bash
javac Wzt.java
```

### Run

```bash
java Wzt
```

## Project Structure

```
.
├── Wzt.java
└── README.md
```

## Next Steps

- Reorder the conditions as shown above and test different values of `i`
- Read `i` from the user with `Scanner`
- Rewrite the chain with a `switch` statement and compare
