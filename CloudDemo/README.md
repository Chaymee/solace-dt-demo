# Solace Distributed Trace Demo

This project is a demo of the Solace Distributed Trace feature. It showcases how to implement distributed tracing in a distributed system using Solace messaging.

## Table of Contents

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [ProgressNotes](#progressNotes)

## Introduction

In this demo, we demonstrate how to leverage the Solace Distributed Trace feature to trace messages as they flow through a distributed system. We provide step-by-step instructions on how to set up the demo environment and how to run the demo.

## Prerequisites

Before running the demo, make sure you have the following prerequisites:

- Solace PubSub+ event broker installed and running
- Java Development Kit (JDK) installed
- Maven build tool installed

## Installation

To install and set up the demo, follow these steps:

1. Clone the repository: `git clone https://github.com/your-username/solace-dt-demo.git`
2. Navigate to the project directory: `cd solace-dt-demo`
3. Build the project: `mvn clean install`

## Usage

To run the demo, follow these steps:

1. Update the Solace PubSub+ connection details in the configuration file: `src/main/resources/application.properties`
2. Start the demo application: `mvn spring-boot:run`
3. Open a web browser and access the demo application at `http://localhost:8080`

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

## TODO
- [ ] Where to host the collector on cloud
- [ ] Where to host the publisher/subscriber on cloud -> docker containers. Modified publisher and subscriber.  Publisher: TTL, DMQ elig, Retries limit. Subscriber: NACK reject
- [ ] Where to host Solace cloud broker
- [ ] Web dashboard for "running scenarios"
    - Passing state (end to end working flow)
    - Failed state 
    1. Queue is full
    2. Subscriber offline (down) missing spans on the end
    3. DMQ movement: Publish on a topic with a malformed message for a subscriber nack. 
    4. DMQ Movement: Publish on a topic that results in a NACK reject. 
- [ ] Setup a notification plan that alerts when a distributed process fails. (We dont know if this is possible)
- [ ] Observability via Datadog
- [ ] Build a presentation script for the demo.

## ProgressNotes
- created a Postman collection for creating the event broker service in cloud: this failed due to an internal cloud service error.  Had to create manually. 
- Modified existing postman collection to setup the broker config for Distributed Tracing.  I had to change the step for client profile modification, we manage that with the could API not semp. 
- Cannot turn on DT with Cloud API sadly. But I was able to setup the collector via the UI after running the postman collection to configure broker. 