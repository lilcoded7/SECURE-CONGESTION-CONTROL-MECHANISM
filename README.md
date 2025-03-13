# Heightened Leaky Bucket Algorithm Documentation

## Installation

Clone the repository with:
```bash
git clone https://github.com/lilcoded7/SECURE-CONGESTION-CONTROL-MECHANISM.git
```

Install dependencies:
```bash
pip install -r requirements.txt
```

## Overview

The Heightened Leaky Bucket Algorithm (HLBA) implements an enhanced version of the traditional leaky bucket algorithm for network traffic management. This documentation covers the implementation details, component integration, and performance analysis results.

## Algorithm Components

### 1. Core Components

- **Leaky Bucket Mechanism**: Controls packet flow using a bucket with specified capacity and leak rate
- **Pascal's Triangle Integration**: Provides lightweight packet encryption/decryption
- **Kadane's Algorithm**: Optimizes packet processing order for improved efficiency

### 2. Key Classes and Methods

#### HeightenedLeakyBucketAlgorithm Class
- `__init__(capacity, leak_rate)`: Initializes the algorithm with specified bucket capacity and leak rate
- `generate_pascals_triangle(rows)`: Generates Pascal's Triangle for packet encryption
- `kadane_algorithm(arr)`: Implements Kadane's algorithm for subarray optimization
- `encrypt_packet(packet, pascal_row)`: Encrypts packets using Pascal's Triangle values
- `decrypt_packet(encrypted_packet, pascal_row)`: Decrypts packets
- `optimize_packet_transmission(packet_sizes)`: Determines optimal packet processing order
- `leak()`: Manages packet leaking from the bucket based on elapsed time
- `add_packet(packet)`: Adds packets to the bucket if capacity permits
- `measure_bandwidth(packet, is_hlba)`: Calculates bandwidth usage
- `process_packets(packets)`: Main processing pipeline for packet handling

#### Utility Functions
- `generate_packets(num_packets, packet_size)`: Creates test packets of specified size
- `test_hlba()`: Tests and evaluates HLBA performance against traditional methods

## Implementation Details

### Packet Processing Pipeline

1. **Initialization**: Create HLBA instance with capacity and leak rate
2. **Optimization**: Determine optimal packet transmission order using Kadane's algorithm
3. **Encryption**: Secure packets using Pascal's Triangle-based encryption
4. **Processing**: Add packets to the bucket with controlled flow
5. **Leaking**: Remove packets from the bucket at the specified leak rate
6. **Measurement**: Calculate processing time and bandwidth metrics

### Security Features

The implementation uses Pascal's Triangle for lightweight encryption:
- XOR operation between packet bytes and Pascal's Triangle values
- Row selection optimized for performance
- Minimal computational overhead for small packets

### Optimization Techniques

- Fast packet ordering using Kadane's algorithm
- Vectorized operations for improved performance
- Special handling for small packet counts
- Optimized leaking calculation

## Performance Results

### Test Configuration
- Bucket capacity: 2
- Leak rate: 2
- Packet sizes tested: 5, 10, 30, 70, and 100 bytes
- Number of packets per test: 10

### Processing Time Performance

| Packet Size (bytes) | HLBA (ms) | Traditional (ms) | Improvement % |
|:-------------------:|:---------:|:----------------:|:-------------:|
| 5                   | 0.00034   | 0.04500          | 99.257%       |
| 10                  | 0.08988   | 1.31549          | 93.167%       |
| 30                  | 0.11015   | 1.37316          | 91.978%       |
| 70                  | 0.24319   | 2.83927          | 91.435%       |
| 100                 | 0.29445   | 3.41269          | 91.372%       |

### Bandwidth Efficiency

All packet sizes showed consistent bandwidth improvements:
- HLBA Bandwidth: 8000.00 bps
- Traditional Bandwidth: 6800.00 bps
- Bandwidth Improvement: 17.65%

## Key Findings

1. **Processing Time**: HLBA demonstrates significant time efficiency, with a 99.257% improvement for 5-byte packets
2. **Consistent Performance**: Maintains high performance across various packet sizes
3. **Bandwidth Efficiency**: Shows a consistent 17.65% bandwidth improvement across all packet sizes
4. **Scalability**: Performance advantage maintained for larger packet sizes

## Practical Applications

The HLBA is particularly effective for:
- Edge computing environments with bandwidth constraints
- Applications requiring secure packet transfer
- Systems sensitive to network congestion
- Scenarios where minimal processing delay is critical

## Conclusion

The Heightened Leaky Bucket Algorithm successfully integrates Pascal's Triangle for security and Kadane's Algorithm for optimization, significantly enhancing the traditional Leaky Bucket Algorithm. The implementation demonstrates substantial improvements in both processing time and bandwidth efficiency, confirming its effectiveness for secure and efficient packet management in network environments.
