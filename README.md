# tempratureconversion
Build a Temperature Conversion Program

#include <stdio.h>

double celsius_to_fahrenheit(double celsius) {
    return (celsius * 9/5) + 32;
}

double celsius_to_kelvin(double celsius) {
    return celsius + 273.15;
}

double fahrenheit_to_celsius(double fahrenheit) {
    return (fahrenheit - 32) * 5/9;
}

double fahrenheit_to_kelvin(double fahrenheit) {
    return (fahrenheit - 32) * 5/9 + 273.15;
}

double kelvin_to_celsius(double kelvin) {
    return kelvin - 273.15;
}

double kelvin_to_fahrenheit(double kelvin) {
    return (kelvin - 273.15) * 9/5 + 32;
}

int main() {
    char original_unit;
    double temperature;

    printf("Temperature Conversion Program\n");
    printf("Available Units: Celsius (C), Fahrenheit (F), Kelvin (K)\n");

    printf("Enter the original temperature unit (C/F/K): ");
    scanf(" %c", &original_unit);

    printf("Enter the temperature value: ");
    scanf("%lf", &temperature);

    if (original_unit == 'C') {
        double fahrenheit = celsius_to_fahrenheit(temperature);
        double kelvin = celsius_to_kelvin(temperature);
        printf("%.2lf C is equal to %.2lf F and %.2lf K\n", temperature, fahrenheit, kelvin);
    } else if (original_unit == 'F') {
        double celsius = fahrenheit_to_celsius(temperature);
        double kelvin = fahrenheit_to_kelvin(temperature);
        printf("%.2lf F is equal to %.2lf C and %.2lf K\n", temperature, celsius, kelvin);
    } else if (original_unit == 'K') {
        double celsius = kelvin_to_celsius(temperature);
        double fahrenheit = kelvin_to_fahrenheit(temperature);
        printf("%.2lf K is equal to %.2lf C and %.2lf F\n", temperature, celsius, fahrenheit);
    } else {
        printf("Invalid unit. Please enter C, F, or K.\n");
    }

    return 0;
}
