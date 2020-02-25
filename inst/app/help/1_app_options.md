### Sidebar Menus
- Each item in sidebar is a step in workflow. 
  - Bolded item with green icon are core steps. Each core step need previous core steps as precondition (except Map can be used right after Visualization, just without home range part). 
  - Italic item with blue icon are optional steps. They require previous core steps as precondition, but optional steps themselves are independent to each other.

### Record Actions
- Every meaningful actions by user can be recorded and compiled into a html work report. All plots and most tables are also saved. This can be turned off to improve performance.

### Collect Diagnostic Info
- If enabled, warning and error messages will be captured by app instead of showing up in R console. Click `Diagnostic Info` button on side bar to show them. This is mainly intended for use in hosted mode as the R console is not available to web users.

### Disable Parallel Mode
- Parallel mode can be tricky. Turning it off can help to isolate and locate the problems. When disabled, you will also see model fitting progress messages in console, which is not visible in parallel mode because they are in cluster/forked process instead of current R process.

### Report
- If app is running locally, `Preview Report` will compile current recordings into a html report, and open it in a new browser window.
- If app is running in hosted server, report cannot be opened automatically because of security limits. It has to be downloaded with `Download Report` then you can open it.

### Save Progress
- `Save Progress` button in side bar will save these data as a zip:
  - `input_telemery.rds`: the telemetry objects of input data
  - `combined_data_table.csv`: the current data subset in csv format
  - `data.rds`: a list that can be imported into R later with `readRDS`
    - `tele_list`: the telemetry object list with modifications made in app, for example some outliers can be removed, new time subset may be added.
    - `merged`: list of 
      - `data`: the combined `data.table` of all animals 
      - `info`: the summary table
    - `all_removed_outliers`: all rows that were removed as outliers.
  - `cache.zip`: cached calculation results. Exactly same calculation can be finished instantly.
  - `model_list_dt.rds`: a `data.table` of all fitted models with related information, and the ctmm model object can be accessed from `model_list_dt$model`, which is a list column.
  - `report.html`: work report.
  - `plot.zip`: the plots saved as `png` or `pdf` files.
  - `error_log.txt` error messages if they are captured in the app instead of R console.
- `Plot DPI` control the dpi of saved plot pictures. You can resize the app to change the plot size.
- The zip can be imported later by `Restore Progess` button in `import` page. Thus you can restore previoius data and cache. Note the app data format may evolve and old saved data may not work with newer version app. You can always use the exactly same version app if needed.
- If you made some changes to the original input data like removed outliers, added time subsets, you can save the changes through `Save Progress`. Later you can restore the csv data through `combined_data_table.csv`, the more complete data through `data.rds`, or whole data zip through `Restore Progess`.
