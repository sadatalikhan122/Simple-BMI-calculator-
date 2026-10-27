# BMI Calculator (Python)

A simple command-line **Body Mass Index (BMI) Calculator** built with Python. It asks for your height and weight, calculates your BMI, and displays a color-coded result alongside a fun ASCII-art welcome screen.

## Features

- Interactive inputs for height and weight
- Automatic conversion from centimeters to meters
- BMI calculation using the standard formula
- Color-coded messages for different BMI categories (in terminals that support ANSI colors)
- Runs with Python only—no additional packages required

## Technologies Used

- **Python 3**
- Basic Python concepts: `input()`, `print()`, arithmetic, `if` / `elif`, and ANSI escape codes

## How BMI Is Calculated

\[
\text{BMI} = \frac{\text{Weight in kilograms}}{(\text{Height in meters})^2}
\]

For example, if your height is **170 cm** and your weight is **65 kg**:

1. Height in meters: `170 / 100 = 1.70`
2. BMI: `65 / (1.70 ** 2) = 22.49`

## Getting Started

1. Install [Python 3](https://www.python.org/downloads/) if you haven't already.
2. Save the BMI calculator code in a file called **`bmi_calculator.py`**.
3. Open a terminal in the folder containing the file and run:

   ```bash
   python bmi_calculator.py
   ```

   On some systems, use `python3 bmi_calculator.py` instead.

4. Enter your **height in centimeters** and **weight in kilograms** when prompted.

## Example Output

```text
welcome to calculate Body mass Index

Enter  you height:170
Enter  you weight:65
your Body Mass index Is ==22.49134948096886
Congratulation you are healhty
```

> The program prints a small ASCII-art figure at startup. Category messages may appear in different colors depending on terminal support.

## BMI Categories

The original program is intended to use these common **adult** BMI categories:

| BMI | Category | Text color |
| --- | --- | --- |
| Below 18.5 | Underweight | Red |
| 18.5 to less than 25 | Healthy range | Green |
| 25 to less than 30 | Overweight | Yellow |
| 30 or above | Obesity range | Blue |

**Note about the current code:** The `elif` conditions check `18.5 <= result <= 24.9`, `25.0 <= result <= 29.9`, and `result > 30.0`. Because BMI is a floating-point number, values such as **24.95**, **29.95**, and **exactly 30.0** do not match any category. To cover all values, replace the category checks with:

```python
if result < 18.5:
    print("\033[91mUnderweight\033[0m")
elif result < 25:
    print("\033[92mHealthy range\033[0m")
elif result < 30:
    print("\033[93mOverweight\033[0m")
else:
    print("\033[94mObesity range\033[0m")
```

## Suggested Project Structure

```text
BMI-Calculator/
├── bmi_calculator.py
└── README.md
```

## Future Improvements

- Validate input and reject zero, negative, or non-numeric height and weight.
- Use `float(input(...))` to accept decimal measurements.
- Round the calculated BMI to two decimal places with `f"{result:.2f}"`.
- Add an option to calculate BMI again without restarting the program.
- Add unit selection for centimeters/inches and kilograms/pounds.

## Disclaimer

BMI is a general screening measure, **not a medical diagnosis**. It does not directly measure body fat or account for all individual differences. Consult a qualified health professional for personalized interpretation.

## License

You can add a license (such as MIT) if you plan to make the repository openly reusable.
