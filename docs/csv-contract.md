# Job Listing CSV Contract

| Field | Required | Format | Example | Reason |
|---|---|---|---|---|
| external_id | Yes | Text, unique | SEEK-1001 | Identifies a listing and prevents duplicate imports |
| title | Yes | Text | Software Engineer | Identifies the advertised role |
| company | Yes | Text | Datacom | Enables analysis by employer |
| location | Yes | City name | Auckland | Enables demand comparison by location |
| seniority | Yes | Junior, Intermediate, Senior, or Unknown | Junior | Enables demand comparison by experience level |
| description | Yes | Long text | Build Java and React applications | Provides the text used to extract technical skills |
| posted_date | Yes | YYYY-MM-DD | 2026-04-02 | Enables reliable date filtering and sorting |
| source_url | Yes | Complete HTTPS URL | https://example.com/jobs/1001 | Preserves the original source for verification |