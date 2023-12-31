# Homebridge Docker Setup

This project sets up a Docker container for running Homebridge on a Raspberry Pi, including the Raspberry Pi Zero with ARM6 architecture, using the `balenalib/raspberry-pi-debian` base image.

## Installation

1. Install Docker on your Raspberry Pi, including the Raspberry Pi Zero, if you haven't already. Make sure to use the appropriate installation instructions for your Docker version and ARM architecture.

2. Clone this repository to your Raspberry Pi.

3. Build the Homebridge Docker image by running the following command in the project directory:
    ```shell
    docker compose build
    ```

   If you are using an older version of Docker that doesn't support `docker compose` command-line, you can use the following command instead:
    ```shell
    docker-compose build
    ```

   Note: The `docker compose` command-line is available starting from Docker version 1.27.0. If you are using an older version, you may need to upgrade Docker or use `docker-compose` command-line.

4. Start the Homebridge container by running the following command:
    ```shell
    docker compose up -d
    ```

   If you are using an older version of Docker, use the following command instead:
    ```shell
    docker-compose up -d
    ```

5. Verify that Homebridge is running by checking the container logs:
    ```shell
    docker compose logs -f homebridge
    ```

   For older versions of Docker, use the following command:
    ```shell
    docker-compose logs -f homebridge
    ```

## Configuration

The configuration for Homebridge is stored in the `.docker-data` volume. You can edit the `config.json` file in the `.docker-data` directory to customize your Homebridge setup.

## Logging

The Homebridge container uses the `json-file` logging driver with a maximum log size of 10MB and a single log file. You can adjust these settings in the `docker-compose.yaml` file if needed.

## Troubleshooting

If you encounter any issues, you can refer to the Homebridge documentation for troubleshooting steps or open an issue in this repository.

Please note that for the Raspberry Pi Zero with ARM6 architecture, you may need to ensure that the necessary dependencies and packages are compatible with ARM6. Some Homebridge plugins or packages may have specific requirements that need to be addressed.

## Contributing

Contributions are welcome! If you have any improvements or bug fixes, feel free to submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).


