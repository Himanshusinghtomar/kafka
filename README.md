
# Kafka-Zookeeper Docker Setup

This repository contains a simple `docker-compose.yml` file to run Kafka and Zookeeper using Docker. You can use this configuration on any machine to set up Kafka and Zookeeper locally or on a remote server.

## Prerequisites

- Ensure Docker and Docker Compose are installed on your machine. If not, install Docker from [here](https://docs.docker.com/get-docker/) and Docker Compose from [here](https://docs.docker.com/compose/install/).

## How to Use

1. **Clone this repository**:
   ```bash
   git clone https://github.com/your-username/kafka-zookeeper-docker.git
   cd kafka-zookeeper-docker
   ```

2. **Adjust Public IP**:
   In the `docker-compose.yml` file, update `KAFKA_ADVERTISED_LISTENERS` to use your machine's public IP address or domain name instead of `localhost`.
   
   Example:
   ```yaml
   KAFKA_ADVERTISED_LISTENERS: PLAINTEXT://<your-public-ip>:9092
   ```

3. **Open Ports**:
   Ensure that the following ports are open in your firewall/security groups (if using cloud services like AWS EC2):
   - **2181** for Zookeeper
   - **9092** for Kafka

4. **Run the services**:
   Start Kafka and Zookeeper using Docker Compose:
   ```bash
   docker-compose up -d
   ```

5. **Access Kafka**:
   Kafka will be available at `<your-public-ip>:9092`, and Zookeeper at `<your-public-ip>:2181`.

6. **Verify Setup**:
   Check if the containers are running by executing:
   ```bash
   docker ps
   ```

## Notes
- You can change other environment variables in the `docker-compose.yml` file according to your requirements.
- For production use, ensure that your configuration is properly secured.

## License
This project is open-source and licensed under the MIT License.
