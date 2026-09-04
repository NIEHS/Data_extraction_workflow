# MoVIZ Data Extraction Workflow v1.0.0

> [!NOTE]
> Version 1.0.0 is the legacy Conda-based release. For easier installation,
> API-call fixes, and updated LLM options, use the
> [latest release](https://github.com/Moreira-Filho/Data_extraction_workflow/releases/latest).

This workflow accompanies the publication **Automating Data Extraction from
Scientific Literature and General PDF Files Using Large Language Models and
KNIME: An Application in Toxicology**.

## Version 1.0.0 Files

- [KNIME workflow](Data%20Extraction%20Workflow%20-%2058%20-%20Publication.knwf)
- [KNIME archive](data.knar)
- [Conda environment](environment.yml)
- [Published v1.0.0 snapshot](https://github.com/Moreira-Filho/Data_extraction_workflow/tree/v1.0.0)

## Installation

### Prerequisites - Python and Packages

Before you can use the workflow, you will need to install its dependencies with Anaconda.
If you don't have it already, download [miniconda3](https://docs.anaconda.com/free/miniconda/).

To install the dependencies:

1. Download the [environment.yml](environment.yml) file.
2. Open the Anaconda/Miniconda terminal.
3. Navigate to the folder containing `environment.yml`.
4. Run the following command: `conda env create -f environment.yml`. Press `y` to confirm the install if prompted.
5. Wait for the packages to install. This may take a while.

### Prerequisites - GROBID

- [GROBID Installation Guide](https://grobid.readthedocs.io/en/latest/Install-Grobid/)
    - **Requires JAVA:**
      For building GROBID yourself, a JDK must be installed on your machine. We tested the tool successfully from JDK 1.11 up to JDK 1.17. Other recent JDK versions should work correctly.
    - **Source Code Download:**
      - Download from GitHub: [grobid-0.8.0.zip](https://github.com/kermitt2/grobid/archive/0.8.0.zip)
      - Unzip the folder `grobid-0.8.0`
      - Place it in a folder without any spaces in the name
    - **Building and Running GROBID:**
      1. Navigate to the `grobid-0.8.0` folder:
          - `cd grobid-0.8.0`
      2. Run the build command:
          - `./gradlew clean install`
      3. Start the local server with the command:
          - `./gradlew run`
          - Check the server at: [http://localhost:8070/](http://localhost:8070/)
      4. **Important:** Ensure the local server is started **before** executing the workflow.
    - **Platform Note:**
      - [Windows-related issues](https://grobid.readthedocs.io/en/latest/Troubleshooting/#windows-related-issues):
        Windows, unfortunately, is currently not supported, due to lack of experience and time constraints.

### Running the Workflow

To set up the workflow on your computer:

1. Download the [version 1.0.0 workflow](Data%20Extraction%20Workflow%20-%2058%20-%20Publication.knwf).
2. In KNIME Analytics Platform, select your **Local Space**.
3. In your local space, select **Import Workflow**.
4. Browse to the workflow file you downloaded; it will have the **.knwf** extension.
5. KNIME may prompt you to install extensions; follow the on-screen instructions to do so. You may need to restart KNIME when done.
6. Once KNIME restarts, open File > Preferences. In the left panel, navigate to KNIME > Conda. Click Browse or enter the path to your Anaconda/Miniconda installation (On Windows, this will often be in your AppData or User folder).
7. Exit Preferences and run the workflow with your data.
