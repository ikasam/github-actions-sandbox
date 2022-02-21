# GitHub Actions の謎を解決するために生まれた

# GitHub Release でトリガーされる GitHub Actions の event

| 事前条件                  | ターゲット  | 操作                    | 発行 event                      | 備考                                    |
| ------------------------- | ----------- | ----------------------- | ------------------------------- | --------------------------------------- |
|                           | Release     | Save draft              | N/A                             |                                         |
|                           | Release     | Publish                 | created, published, released    |                                         |
| Release を Save Draft     | Release     | Publish                 | published, released             |                                         |
| Pre-release を Save Draft | Release     | Publish                 | published, released             |                                         |
| Release を Publish        | Release     | body を編集して Publish | edited                          |                                         |
|                           | Pre-release | Save draft              | N/A                             |                                         |
|                           | Pre-release | Publish                 | created, published, prereleased |                                         |
| Release を Save Draft     | Pre-release | Publish                 | published, prereleased          |                                         |
| Pre-release を Save Draft | Pre-release | Publish                 | published                       |                                         |
| Release を Publish        | Pre-Release | Publish                 | prereleased                     | body を編集していても edit は発火しない |
