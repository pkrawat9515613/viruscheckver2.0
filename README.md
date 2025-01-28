# viruscheckver2.0

VirusTotal IP Report Generator

This script allows you to query the VirusTotal API for a list of IP addresses provided in a CSV file. It will generate a report for each IP, showing whether it is malicious, harmless, suspicious, or undetected based on VirusTotal's analysis. The results are written to a new CSV file.
Prerequisites

    Python 3.x

    Install the required libraries using pip:

    pip install requests
    pip install tk

    A valid VirusTotal API key. You can obtain one by signing up on VirusTotal's website.

Usage

    Prepare your input CSV file: The input file should contain a list of IP addresses, one per row, with no header.

    Run the script: Open the script and run it. The GUI will open, allowing you to:
        Browse and select your input CSV file (with the list of IP addresses).
        Specify where to save the output CSV file.

    Start the analysis: Click the "Generate Report" button to begin the IP address analysis. The progress bar will show the processing status.

    Results: After the process is complete, the results will be saved in the output CSV file you specified. The output file will contain:
        IP Address
        Malicious count
        Harmless count
        Suspicious count
        Undetected count
        Timeout count
        A link to the VirusTotal page for each IP address

Features

    VirusTotal API Integration: Uses the VirusTotal API to gather data about each IP address.
    CSV Input/Output: The program works with CSV files for easy handling of IP addresses.
    Tkinter GUI: A user-friendly graphical interface to browse for files and display progress.
    Progress Monitoring: A progress bar and percentage display to track the analysis process.

How It Works

    The script reads the IP addresses from the input CSV file.
    It sends a request to the VirusTotal API for each IP address.
    The script parses the response and gathers information about the IP's status.
    It writes the results to an output CSV file.

Code Explanation

    query_virustotal(ip_address): Sends a GET request to the VirusTotal API with the provided IP address and retrieves the analysis results.

    process_ips(): Main function that reads the input CSV, processes each IP address, and generates the output CSV with the analysis results.

    browse_input_file() and browse_output_file(): These functions open file dialogs to allow the user to select the input and output files.

    Tkinter GUI: The GUI is built using the tkinter and ttk modules. It provides fields for selecting the input and output files, and a progress bar to show the status of the process.

Example Output CSV
IP Address	Malicious	Harmless	Suspicious	Undetected	Timeouts	VirusTotal Link
192.168.1.1	5	0	2	0	0	VirusTotal Link
10.0.0.1	0	10	1	0	0	VirusTotal Link
Notes

    Rate Limiting: The script includes a small delay (time.sleep(0)) to avoid hitting the API rate limit. You may need to adjust the sleep duration based on your API plan.

    Error Handling: If the API returns an error, or if the IP address has no analysis data available, the report will display "No data available" or "Error retrieving data".

Troubleshooting

    Invalid API Key: If you receive an error stating that the API key is invalid, double-check that you’ve replaced the placeholder API_KEY with your actual key.

    No Data for an IP: If no analysis data is available for an IP address, the script will log "No data available" for that entry.

License

This script is open-source and available for modification and redistribution under the MIT License.
