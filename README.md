# Homebridge Docker Setup

This project sets up a Docker container for running Homebridge on a Raspberry Pi using the `balenalib/raspberry-pi-debian` base image.

## Installation

1. Install Docker on your Raspberry Pi if you haven't already.

2. Clone this repository to your Raspberry Pi.

3. Build the Homebridge Docker image by running the following command in the project directory:
    ```shell
    docker-compose build
    ```

4. Start the Homebridge container by running the following command:
    ```shell
    docker-compose up -d
    ```

5. Verify that Homebridge is running by checking the container logs:
    ```shell
    docker-compose logs -f homebridge
    ```

## Configuration

The configuration for Homebridge is stored in the `.docker-data` volume. You can edit the `config.json` file in the `.docker-data` directory to customize your Homebridge setup.

## Logging

The Homebridge container uses the `json-file` logging driver with a maximum log size of 10MB and a single log file. You can adjust these settings in the `docker-compose.yml` file if needed.

## Troubleshooting

If you encounter any issues, you can refer to the Homebridge documentation for troubleshooting steps or open an issue in this repository.

## Contributing

Contributions are welcome! If you have any improvements or bug fixes, feel free to submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).
