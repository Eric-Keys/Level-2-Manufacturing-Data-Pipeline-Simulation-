# Level-2-Manufacturing-Data-Pipeline-Simulation-
A simulation deploying a C# .NET data pipeline to an Oracle Express Multitenant database environment.


## Architectural Highlight & Troubleshooting Case Study
During the initial deployment of this pipeline integration sample, data transmission failed with an `ORA-00942` error. 

The root cause was diagnosed as an environment mismatch: the database tables were provisioned inside the root container instance (`XE`), whereas the application's default data source profile was targeting the pluggable database (`XEPDB1`). 

### Resolution:
* Navigated the Oracle Multitenant container hierarchy via SQL*Plus to align the database environment.
* Successfully opened and isolated the `XEPDB1` pluggable workspace container.
* Reconfigured the C# database connection string and network layout data source routing to clear the pipeline.

## Technical Capabilities Demonstrated
* **Database Infrastructure:** Navigating Oracle Multitenant database architecture (`XE` vs `XEPDB1`).
* **Pipeline Security:** Implementing parameterized `OracleCommand` data bindings (`:machine`, `:weight`) to enforce strict type constraints and neutralize SQL injection vectors.
* **Defensive Coding Integration:** Adapting C# null-coalescing operations (`?? ""`) to gracefully handle unexpected asynchronous terminal stream faults without halting the execution thread.

## Pictures
<img src="programmer%20practice/pictures/Screenshot%202026-06-23%010535.png" width="800">
<img src="pictures/Screenshot%202026-06-23%012759.png" width="800">
<img src="pictures/Screenshot%202026-06-23%024042.png" width="800">
<img src="pictures/Screenshot%202026-06-23%024139.png" width="800">
