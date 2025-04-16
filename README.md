# ClickHouse Data Transfer Tool

A web application designed for seamless bidirectional data transfer between ClickHouse databases and flat files.

## Key Features

- **Bidirectional Data Flow**:
  - Export data from ClickHouse to Flat Files (CSV, JSON, TSV)
  - Import data from Flat Files to ClickHouse

- **ClickHouse Integration**:
  - Connect to ClickHouse using host, port, database, and user credentials
  - Support for JWT token-based authentication
  - SSL/HTTPS secure connection options

- **Flat File Support**:
  - Compatible with CSV, TSV, and other delimited file formats
  - Customizable delimiter configuration
  - Automatic schema detection

- **Advanced Data Handling**:
  - Schema discovery and auto-mapping
  - Select columns for export/import
  - Data type inference
  - Table creation support
  - Custom column mapping options

- **User-Friendly Interface**:
  - Easy-to-navigate and intuitive UI
  - Real-time connection testing
  - Data preview features
  - Progress reporting
  - Robust error handling

## Setup Instructions

### Prerequisites

- Python 3.8 or higher
- Node.js 14 or higher
- npm or yarn
- Access to a ClickHouse database

### Backend Setup

1. Clone the repository and move to the backend directory:

    ```bash
    git clone https://github.com/TushaS004/Zeotap.git
    cd Zeotap2
    ```

2. Create and activate a virtual environment:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows: venv\Scripts\activate
    ```

3. Install the necessary dependencies:

    ```bash
    pip install fastapi uvicorn clickhouse-driver pandas python-multipart
    ```

4. Start the backend server:

    ```bash
    uvicorn main:app --reload --host 0.0.0.0 --port 8000
    ```

### Frontend Setup

1. Navigate to the frontend directory:

    ```bash
    cd ../Frontend
    ```

2. Install the required dependencies:

    ```bash
    npm install
    # or
    yarn install
    ```

3. Start the development server:

    ```bash
    npm run dev
    # or
    yarn start
    ```

    The application will be accessible at http://localhost:3000 by default.

## How to Use

### Exporting Data from ClickHouse to Flat File

1. Select the "ClickHouse → Flat File" option.
2. Enter your ClickHouse connection details and test the connection.
3. Choose the database and table from which you want to export data.
4. Select the columns to be included in the export.
5. Choose your preferred export format (CSV, JSON, TSV).
6. Optionally, provide a custom filename.
7. Click "Export Data" to download the file.

### Importing Data from Flat File to ClickHouse

1. Select the "Flat File → ClickHouse" option.
2. Enter your ClickHouse connection details and test the connection.
3. Upload a flat file and select the delimiter type.
4. Review the automatically detected schema.
5. Provide the target table name.
6. Configure the column mapping if needed.
7. Choose to create the table if it doesn't already exist.
8. Click "Import Data" to begin the import process.

## Environment Variables

The backend supports the following environment variables:

- `CLICKHOUSE_HOST`: Default ClickHouse host (default: "localhost")
- `CLICKHOUSE_PORT`: Default ClickHouse port (default: 9000)
- `CLICKHOUSE_USER`: Default ClickHouse user (default: "default")
- `CLICKHOUSE_PASSWORD`: Default ClickHouse password (default: "")
- `CLICKHOUSE_DATABASE`: Default ClickHouse database (default: "default")
- `CORS_ORIGINS`: Allowed CORS origins, comma-separated (default: "*")

## Security Considerations

- By default, the application uses HTTP. For production, it is recommended to configure HTTPS.
- JWT tokens and passwords are transmitted over the network. Ensure secure connections for production environments.
- The application lacks user authentication by default. For production deployment, consider adding an authentication layer.

## Error Handling

The application provides detailed error messages for issues such as:
- Connection problems
- Authentication failures
- Schema detection issues
- Import/export failures
- File format problems

## License

This project is licensed under the MIT License. See the LICENSE file for further details.
