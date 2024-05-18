<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lead Acid Battery Charger with Constant Current and Constant Voltage Control</title>
</head>
<body>
    <h1>Lead Acid Battery Charger with Constant Current and Constant Voltage Control</h1>

    <h2>Introduction</h2>
    <p>Each battery has its own charging profile, and to maintain a healthy battery, this profile should be followed correctly. Typically, a charging profile consists of a constant current (CC) stage followed by a constant voltage (CV) stage. This project aims to design a power source capable of operating in both conditions to charge a 12V lead acid battery.</p>

    <h2>Project Overview</h2>
    <p>This project involves designing a constant current source to charge a 12V lead acid battery with a maximum charging current of 1A. The input voltage for the system is 230V AC, and the system is based on the Pulse Width Modulation (PWM) technique. Additionally, a suitable enclosure is designed to house all the circuits in a safe and ergonomic manner.</p>

    <h2>Requirements</h2>
    <ul>
        <li><strong>Constant Current Source:</strong> To charge a 12V lead acid battery with a maximum charging current of 1A.</li>
        <li><strong>Input Voltage:</strong> 230V AC.</li>
        <li><strong>PWM Technique:</strong> Used for controlling the charging process.</li>
        <li><strong>Enclosure Design:</strong> A safe and ergonomic enclosure to house all circuits.</li>
    </ul>

    <h2>Methodology</h2>
    <p>The charging process is divided into two stages:</p>

    <h3>1. Constant Current Mode</h3>
    <p>During the constant current stage, the battery is charged at a fast rate with a constant current of 1A. The internal resistance of the battery gradually increases, raising the voltage across the battery until it reaches around 13.3V.</p>

    <h3>2. Constant Voltage Mode</h3>
    <p>Once the battery voltage reaches 13.3V, the charger maintains a steady voltage. The charging current slows down due to the increased resistance, filling up the remaining 30% of the battery at a slower rate.</p>

    <h2>Circuit Components</h2>

    <h3>PWM Generator</h3>
    <p>This circuit generates a PWM signal with a high frequency and adjustable duty cycle using two NE555 timer ICs in astable and monostable modes. The duty cycle is adjusted by the input to the voltage controller pin in the second IC.</p>

    <h3>Constant Current Controller</h3>
    <p>This circuit ensures the battery receives a constant 1A current during the initial 70% of charging. A differential amplifier provides 5V when the current is 1A, which is fed to a comparator circuit that adjusts the PWM generator accordingly.</p>

    <h3>Constant Voltage Controller</h3>
    <p>This circuit maintains a constant 13.3V during the final 30% of charging. A differential amplifier provides 5V when the voltage is 13.3V, which is also fed to a comparator circuit that adjusts the PWM generator.</p>

    <h3>Switching Circuit</h3>
    <p>This circuit uses an OP747 opamp comparator to switch between constant current and constant voltage modes based on the battery voltage.</p>

    <h3>Buck Converter</h3>
    <p>The buck converter works in conjunction with the switching circuit to regulate the charging process, ensuring the battery is charged correctly in both stages.</p>

    <h2>Implementation</h2>
    <p>The circuit was implemented on a breadboard to verify its functionality.</p>

    <h3>Results</h3>
    <ul>
        <li><strong>PWM output without buck converter:</strong> Verified to be functional.</li>
        <li><strong>PWM output changing due to control voltage:</strong> Observed and documented.</li>
    </ul>

    <h2>Conclusion</h2>
    <p>This project successfully demonstrates a power source that can operate in both constant current and constant voltage modes to charge a 12V lead acid battery efficiently and safely.</p>

    <h2>Repository Structure</h2>
    <ul>
        <li><strong>/schematics</strong> - Circuit schematics and diagrams.</li>
        <li><strong>/code</strong> - Any code or scripts used in the project.</li>
        <li><strong>/documentation</strong> - Project documentation and reports.</li>
        <li><strong>/enclosure_design</strong> - Files related to the enclosure design.</li>
    </ul>

    <h2>Getting Started</h2>
    <ol>
        <li>Clone the repository:
            <pre><code>git clone https://github.com/your-username/lead-acid-battery-charger.git</code></pre>
        </li>
        <li>Follow the instructions in the <strong>/documentation</strong> folder to set up the circuit and test the functionality.</li>
    </ol>

    <h2>Contributions</h2>
    <p>Feel free to submit issues, fork the repository, and send pull requests. Contributions are welcome!</p>

    <h2>License</h2>
    <p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details.</p>

    <h2>Contact</h2>
    <p>For any inquiries, please contact <a href="mailto:your-email@example.com">your-email@example.com</a>.</p>
</body>
</html>
