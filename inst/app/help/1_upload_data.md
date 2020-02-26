
### Upload Data
- Data must be (multiple) (compressed) csv file in [Movebank format](https://www.movebank.org/node/13).
- The csv file can be compressed in `zip`, `gz`, `bzip` etc, but there can only be one file in a zip.
- You can drag and drop files into the file uploader. Multiple files upload is not supported by all browsers. Chrome is the recommended browser.

### Restore Progress
- Using `Save Progress` button in sidebar to save input data, cached calculation results and work report.
- Uploading the saved zip with `Restore Progress` will restore the input data and previous caches.
  - Note this will only restore input data, not the latter stages of workflow. Because the workflow depend on lots of user interactions (table row selection, plot selection) and often need to wait app update to finish before going to next step, it's not possible to reproduce every user interaction programmingly to reach the exact same stage when saving progress.
  - However, the consuming operations like model selection, home range and occurrence can be finished instanly because of cache, if the calculation is exactly same, i.e. same data and same selections. Note cache will only work with exactly same app package version.
- The saved work report is also opened for reference if app is running in local mode.

