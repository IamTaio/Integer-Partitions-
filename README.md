# Integer Partitions Generator

A Flask web application that efficiently generates and counts integer partitions following specific mathematical identities and constraints.

## Project Overview

This application implements algorithms to generate and enumerate integer partitions following three important mathematical identities:
- First Rogers-Ramanujan Identity
- Rogers-Ramanujan-Gordon Identity
- Capparelli's First Identity

### Key Features
- Dynamic generation of integer partitions
- Partition counting functionality
- Support for multiple mathematical identities
- Web-based interface for easy access
- Efficient algorithms using functional equations and dynamic programming

### Technologies Used
- Python 3.x
- Flask
- HTML/Jinja2 Templates

## Problem Statement

### Integer Partitions
A partition of an integer n is a sequence of positive integers that sum to n. For example, the integer 4 has five partitions:
- 4
- 3 + 1
- 2 + 2
- 2 + 1 + 1
- 1 + 1 + 1 + 1

This application focuses on generating partitions that satisfy specific conditions defined by well-known mathematical identities.

### Supported Identities

1. **First Rogers-Ramanujan Identity**
   - Generates partitions where successive parts differ by at least 2
   - Example: For n=6, valid partitions include [6], [5,1], [4,2]

2. **Rogers-Ramanujan-Gordon Identity**
   - Generalization of Rogers-Ramanujan identity
   - Parameters: n (integer), m (parts), k (distance), max_ones
   - Generates partitions with controlled part differences and limitations on ones

3. **Capparelli's First Identity**
   - Generates partitions where parts differ by at least 2
   - Special condition: parts can differ by less than 4 if they sum to a multiple of 3
   - Example: For n=10, valid partitions include [10], [8,2], [7,3]

## Implementation Details

### Core Components

1. **Partition Generation Algorithms (`Algos.py`)**
   - `ListRRGpartitions()`: Generates Rogers-Ramanujan-Gordon partitions
   - `capgenerator()`: Generates Capparelli partitions
   - `mRogerRG()`: Counts Rogers-Ramanujan-Gordon partitions
   - `capcounter()`: Counts Capparelli partitions

2. **Web Interface (`app.py`)**
   - Flask routes for handling user input
   - Form processing for different partition types
   - Result display formatting

### Algorithm Approach
- Uses functional equations for partition generation
- Implements dynamic programming for efficient computation
- Avoids recursive calls to optimize performance
- Maintains partition validity through equation-based generation

## Installation and Usage

1. **Prerequisites**
   ```bash
   Python 3.x
   pip
   ```

2. **Installation**
   ```bash
   # Clone the repository
   git clone [repository-url]

   # Install dependencies
   pip install -r requirements.txt
   ```

3. **Running the Application**
   ```bash
   python app.py
   ```
   The application will be available at `http://localhost:5000`

### Using the Web Interface

1. Select the desired partition identity:
   - Rogers-Ramanujan
   - Rogers-Ramanujan-Gordon
   - Capparelli

2. Choose the operation:
   - Counter (returns the number of valid partitions)
   - Generator (returns the list of valid partitions)

3. Enter required parameters:
   - Integer to partition (n)
   - Number of parts (m)
   - Additional parameters for specific identities

## Error Handling

The application handles several types of input validation:
- Non-negative integer inputs
- Valid parameter ranges for each identity
- Maximum computation limits

## Limitations

- Performance may degrade for large integers due to the combinatorial nature of the problem
- Memory usage increases with partition size and complexity
- Web interface timeout limits for very large computations

## Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for:
- Algorithm optimizations
- Additional partition identities
- Interface improvements
- Documentation updates

## License

This project is open-source and available under [specify license].

## Acknowledgments

- Research supervision by Kağan Kurşungöz
- Based on mathematical work by Rogers, Ramanujan, Gordon, and Capparelli
