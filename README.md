# Database Transformation GUI & Polyglot Storage Engine

### 🚀 Key Engineering Achievements
*   **Polyglot Storage Architecture:** Engineered a hybrid data layer that maps relational records to SQL databases while routing unstructured files (PDFs, Word documents) to NoSQL (MongoDB), optimizing both query performance and storage flexibility.
*   **Performance Optimization:** Designed a custom data parsing layer enabling cross-functional teams to smoothly process vast file blocks, **cutting target data retrieval time by up to 80%**.
*   **Extensible Plugin System:** Architected a modular Python-based plugin framework allowing seamless integration of custom data transformation scripts (e.g., batch processing, schema validation) without altering core logic.
*   **Enterprise GUI:** Developed a robust graphical interface for complex database operations (CRUD, conditional updates, batch JSON execution), bridging the gap between heavy backend data engineering and non-technical end-users.

---

*A graphical interface for performing database operations with SQL integration, unstructured document routing, and a dynamic Python plugin system.*

## Features

- **Core Operations**:
  - CRUD (Insert/Update/Delete rows)
  - Column management (Add/Rename/Remove/Merge)
  - Conditional updates
  - Batch operations via JSON scripts

- **Plugin System**:
  - Extend functionality with Python plugins
  - Pre-built plugins: Case conversion, batch inserts
  - Auto-loads plugins from `plugins/` directory

- **Import/Export**:
  - CSV/Excel to SQL table conversion
  - JSON configuration support
  - Schema validation

## Prerequisites

- SQL Server (MySQL 8.0+ / PostgreSQL)
- Python 3.8+
- Required packages:
  ```bash
  pip install pymysql pandas sqlalchemy tk customtkinter jsonschema
  
Configuration
# In database_Ops.py
self.connection = pymysql.connect(
    host="localhost",
    user="root",
    password="your SQL password",  # Change to your credentials
    database="database name"      # Create this database first
)

Project Structure 
- ├── core_operations.json       # Core operation definitions
- ├── database_Ops.py            # Database connection & operations
- ├── GUI.py                     # Main application window
- ├── transformManagerDatabase.py# Database singleton
- ├── plugins/                   # Custom operations
- │   └── lowercase_plugin.py    # Sample plugin
- ├── *.json                     # Operation scripts
  
Execution
When executing, use the provided JSON files (i.e., Rename_column.json, delete_column.json, and merge_columns.json) to run batch transformations.

Plugins Usage
    Place custom plugins in the plugins/ directory.
    Available plugins auto-load on startup.
    Access plugin buttons on the right sidebar of the GUI.
