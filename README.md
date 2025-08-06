# JMeter Performance Test for JSONPlaceholder API

This repository contains a JMeter project for performance testing the public [JSONPlaceholder](https://jsonplaceholder.typicode.com/) API.

The test plan simulates a realistic user workflow:
1.  Fetches all posts.
2.  Selects a random post from the response (using correlation).
3.  Fetches the comments for the selected post.

## ✔️ Prerequisites

* [Java](https://www.java.com/) (version 8 or higher) installed.
* [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi) installed.
* (Recommended) JMeter's `bin` directory added to the system's `PATH` variable for easier execution.

## 🚀 How to Run the Test

The test is intended to be run from the command-line interface (CLI), not from the JMeter GUI.

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Nikolay-Chillev/jmeter-performance-project.git](https://github.com/Nikolay-Chillev/jmeter-performance-project.git)
    cd jmeter-performance-project
    ```

2.  **Run the test:**
    Open a command-line terminal (CMD, PowerShell, bash) in the project's root directory and execute the following command:
    ```bash
    jmeter -n -t jsonplaceholder_load_workflow.jmx -l results/results.jtl -e -o reports/html_report
    ```

3.  **Customize the Load (Optional):**
    You can override the default number of users (threads) and the ramp-up time by passing properties with the `-J` flag:
    ```bash
    # Example with 50 users ramping up over 10 seconds
    jmeter -n -t jsonplaceholder_load_workflow.jmx -Jthreads=50 -Jrampup=10 -l results/results.jtl -e -o reports/html_report
    ```

4.  **View the Report:**
    Once the test is complete, open the `reports/html_report/index.html` file in a web browser to view the full HTML dashboard report with detailed graphs and statistics.

## 📂 Project Structure

* `jsonplaceholder_load_workflow.jmx`: The main JMeter test plan file.
* `/reports/`: The directory where the HTML dashboard reports are generated (ignored by Git).
* `.gitignore`: A configuration file that tells Git which files and folders to ignore.
* `README.md`: This documentation file.
