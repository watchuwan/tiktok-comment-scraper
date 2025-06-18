# TikTok Comment Scraper

A Python-based tool that scrapes and analyzes comments from TikTok videos. This tool allows you to fetch comments, save them in multiple formats, and perform basic analysis on the comment data.

for scrapes in Twitter or X can access in here [Helmi Satria Tweet Harvest](https://helmisatria.com/blog/crawl-data-twitter-menggunakan-tweet-harvest/)

## Features

- Scrape comments from any TikTok video using its video ID
- Save comments in multiple formats:
  - JSON (preserves all data including nested replies)
  - CSV (tabular format for easy analysis)
  - Excel (spreadsheet format)
- Support for comment replies
- Data analysis capabilities:
  - Basic statistics (total comments, unique users)
  - Time analysis of comments
  - Top commenters visualization
  - Word frequency analysis
- Automatic file management:
  - Saves both batch files (e.g., 0-50.json) and consolidated files (full.json)
  - Maintains separate directories for each video ID

## Requirements

- Python 3.x
- Required packages:
  - requests
  - pandas
  - matplotlib
  - openpyxl (for Excel support)

Install the required packages using:

```bash
pip install requests pandas matplotlib openpyxl
```

## Usage

1. Open the Jupyter Notebook `TikTok_Comment_Scraper.ipynb`
2. Replace the `video_id` variable with your desired TikTok video ID
3. Run the notebook cells in sequence

Example code:

```python
# Create an instance of the Comment class
comment = Comment()

# Replace with your TikTok video ID
video_id = "YOUR_VIDEO_ID"
size = 0  # Start from the beginning

# Execute the scraper with multiple save formats
result = comment.execute(video_id, size, save_formats=['json', 'csv', 'excel'])
```

## Output Structure

```
TikTok_Comments/
└── [video_id]/
    ├── 0-50.json        # First batch of comments
    ├── 0-50.csv
    ├── 0-50.xlsx
    ├── full.json        # Consolidated file with all comments
    ├── full.csv
    └── full.xlsx
```

## Data Analysis

The tool provides several analysis features:

- Total number of comments
- Count of unique users
- Average replies per comment
- Time range of comments
- Visualization of top 10 commenters
- Word frequency analysis

You can analyze the data from any saved format:

```python
analyze_comments(video_id, format='json')  # or 'csv' or 'excel'
```

## Note

Make sure you have a valid TikTok video ID before running the code. The video ID can be found in the URL of the TikTok video or through the share link.

## License

This project is for educational purposes only. Make sure to comply with TikTok's terms of service and API usage guidelines when using this tool.
