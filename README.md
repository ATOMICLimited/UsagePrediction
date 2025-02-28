# Usage Prediction Training Data Library

## Overview

The **Usage Prediction Training Data Library** is designed to support the **ATOMIC Usage Prediction Model**, which leverages AI to predict usage trends based on various system metrics. This library incorporates a multi-threaded architecture for processing, ensuring high throughput and fault tolerance.

### Features

- AI-powered usage prediction using TensorFlow.js
- Multi-threaded batch execution with worker threads
- High-performance TPS (Transactions Per Second) tracking for real-time monitoring
- Secure transaction processing with NATO Transport encryption
- Zero-copy execution via RDMA optimization
- Persistent storage and watchdog recovery for fault tolerance

## Installation

To install the library, ensure you have Node.js and npm installed, then run:

```bash
npm install
Processing Prediction Requests
You can process usage prediction requests by calling the process method with your payload. The payload should include usage data in the expected format.

const payload = {
    usageData: [
        { id: '1', cpuLoad: 30, memoryUsage: 70, storageUsage: 20 },
        { id: '2', cpuLoad: 40, memoryUsage: 80, storageUsage: 15 },
        // Add more usage data tasks...
    ],
};

usagePrediction.process(payload)
    .then(result => {
        console.log('Prediction results:', result);
    })
    .catch(error => {
        console.error('Error processing prediction:', error);
    });
Configuration
You can adjust the following configuration variables in your environment:

SKIP_PERSISTENCE: Set to "true" to skip writing to the persistence file (useful during testing).
LOG_LEVEL: Adjust the logging level (e.g., info, debug, error).
Worker Script
The worker script usagePredictionModelWorker.js, included with the library, is responsible for offloading prediction processing. It handles the AI model loading, input data preparation, and managing TPS metrics. 

This script includes important features like:

Loading the neural network model.
Making predictions based on incoming batch data.
Encrypting the results for secure transportation.
Logging
All log messages are recorded using Winston and stored in a specified log file. Make sure to check the logs for debug information or errors if you encounter issues.

Fault Tolerance
The library includes a persistent storage mechanism that preserves in-progress tasks. In case of failure, you can recover tasks based on saved state, ensuring robustness and reliability.

Contributing
Contributions are welcome! If you'd like to contribute to this project, please create a fork and submit a pull request. 

License
SPDX-License-Identifier: ATOMIC-Limited-3.0

Refer to the LICENSE file in this repository for more details.
