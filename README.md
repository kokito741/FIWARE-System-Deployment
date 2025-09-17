# Home Environmental Monitoring – FIWARE System Deployment

This repository contains the deployment and integration files for the Home Environmental Monitoring System using the FIWARE platform. It is designed to receive data from the ESP32 hardware and store it in CrateDB, enabling visualization in Grafana.

## Contents

SmartSDK.postman_collection.json – Postman collection for testing FIWARE endpoints and sending sample data.

crate.yml – Configuration for CrateDB deployment.

docker-compose_final.yml – Docker Compose setup for deploying FIWARE components (Orion Context Broker, IoT Agent, QuantumLeap, CrateDB, Grafana).

## Usage

Import the Postman collection into your workspace to test and verify FIWARE endpoints.

Deploy the system using Docker Compose:
