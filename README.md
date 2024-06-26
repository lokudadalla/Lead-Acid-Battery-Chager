<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
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
        <img src="https://private-user-images.githubusercontent.com/133969661/331798520-b485ea60-d34f-468a-837d-dc1756eb369e.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTYwMzU1NTQsIm5iZiI6MTcxNjAzNTI1NCwicGF0aCI6Ii8xMzM5Njk2NjEvMzMxNzk4NTIwLWI0ODVlYTYwLWQzNGYtNDY4YS04MzdkLWRjMTc1NmViMzY5ZS5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwNTE4JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDUxOFQxMjI3MzRaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT01Y2NkYzE5OTc2MWMwMGZmZmM0MDE1NTZhODNjMjA2ZmNlY2UxMThiMjIxYjYxNjA0YWI1NjE5MDI3MDQwMWJlJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.73XCuM6bYwyLgkHqXzRY9cJYqYkkG9hTmnFokWhEgng" alt="Charger Diagram" width="500">

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
    <img src="https://media.licdn.com/dms/image/D5612AQGUOb3Wp3Picw/article-inline_image-shrink_1500_2232/0/1705651347505?e=1721260800&v=beta&t=mfDjZUKkzgKsvxdE_pWh9dXA_fhWBgqfgBahB-1iqgM" alt="Charger Diagram" width="500">
    <img src="https://media.licdn.com/dms/image/D5612AQHIeHim18oi_g/article-inline_image-shrink_1500_2232/0/1705651366562?e=1721260800&v=beta&t=Aye_njf5LrNSKCeabLDjT0YqZOlG1emfKlHQHpL3mME" alt="Charger Diagram" width="500">
    <h3>Constant Current Controller</h3>
    <p>This circuit ensures the battery receives a constant 1A current during the initial 70% of charging. A differential amplifier provides 5V when the current is 1A, which is fed to a comparator circuit that adjusts the PWM generator accordingly.</p>
    <img src="https://media.licdn.com/dms/image/D5612AQE_VKyaJ5-sKg/article-inline_image-shrink_1500_2232/0/1705651386071?e=1721260800&v=beta&t=CmnTdI5VaeLA1QvCTdFIeFZ2oXuN9qV74god504faJc" alt="Charger Diagram" width="500">
    <img src="https://media.licdn.com/dms/image/D5612AQFuR955E6fxWA/article-inline_image-shrink_1500_2232/0/1705651399231?e=1721260800&v=beta&t=_kOTPGhtNpUBVZvuG9Uh3w1diO2L_X2TQ45CgWnr9CY" alt="Charger Diagram" width="500">
    <h3>Constant Voltage Controller</h3>
    <p>This circuit maintains a constant 13.3V during the final 30% of charging. A differential amplifier provides 5V when the voltage is 13.3V, which is also fed to a comparator circuit that adjusts the PWM generator.</p>
    <img src="https://media.licdn.com/dms/image/D5612AQFXkOTaakZ1oQ/article-inline_image-shrink_1500_2232/0/1705651428109?e=1721260800&v=beta&t=ANI-ND-GKnwCGLX_HIwxFlFgozAo7C1IEKH66mPJDTA" alt="Charger Diagram" width="500">
    <img src="https://media.licdn.com/dms/image/D5612AQFvhRJjL2n72g/article-inline_image-shrink_1500_2232/0/1705651438594?e=1721260800&v=beta&t=uqONWXvrMwERm8nLenTXN3Fkbis0K8szHmSarGBRwgo" alt="Charger Diagram" width="500">
    <h3>Switching Circuit</h3>
    <p>This circuit uses an OP747 opamp comparator to switch between constant current and constant voltage modes based on the battery voltage.</p>
    <img src="https://media.licdn.com/dms/image/D5612AQGEv3kxS8jHJA/article-inline_image-shrink_1500_2232/0/1705651454240?e=1721260800&v=beta&t=RKKdxUTAytcxzypqReLOuPsQpOQHSBKZobEQIXnOvww" alt="Charger Diagram" width="500">
    <h3>Buck Converter</h3>
    <p>The buck converter works in conjunction with the switching circuit to regulate the charging process, ensuring the battery is charged correctly in both stages.</p>
    <img src="https://media.licdn.com/dms/image/D5612AQEvy8CXdE8rGg/article-inline_image-shrink_1500_2232/0/1705651579294?e=1721260800&v=beta&t=nzyI4kiJsuSTcCGWAP1diCLqt3p5QRzCltHfjcMEMSs" alt="Charger Diagram" width="500">
    <h2>Implementation</h2>
    <img src="https://media.licdn.com/dms/image/D5612AQFZc6YyF9UNuw/article-inline_image-shrink_1000_1488/0/1705651656849?e=1721260800&v=beta&t=i8f8Hezrq0qDLw6kBSiOjfFJYSBQJqhku9AN0kol9W8" alt="Charger Diagram" width="500">
    <img src="https://media.licdn.com/dms/image/D5612AQEbsYddoKQKWg/article-inline_image-shrink_1500_2232/0/1705651785195?e=1721260800&v=beta&t=ilp-FqIjsZg1c81_NTgCLLWWyOBK5Yb_GZVMQQEVu_w" alt="Charger Diagram" width="500">
    <p>The circuit was implemented on a breadboard to verify its functionality.</p>
    <h3>Results</h3>
    <ul>
        <img src="https://media.licdn.com/dms/image/D5612AQFXQsijv234-g/article-inline_image-shrink_1500_2232/0/1705651824750?e=1721260800&v=beta&t=W_yapIfjosqM02xUrbHDFTNAvbeKR0QBRGO2UahV8t0" alt="Charger Diagram" width="500">
        <li><strong>PWM output without buck converter:</strong> Verified to be functional.</li>
        <img src="https://media.licdn.com/dms/image/D5612AQG_DthY4KK9DQ/article-inline_image-shrink_1500_2232/0/1705651981114?e=1721260800&v=beta&t=M_Ji8zwRSeuSsrxNbNix8GDnWsmwH5_uwjmqfRKM-EU" alt="Charger Diagram" width="500">
        <li><strong>PWM output changing due to control voltage:</strong> Observed and documented.</li>
    </ul>
    <h2>Conclusion</h2>
    <p>This project successfully demonstrates a power source that can operate in both constant current and constant voltage modes to charge a 12V lead acid battery efficiently and safely.</p>
</body>
</html>
