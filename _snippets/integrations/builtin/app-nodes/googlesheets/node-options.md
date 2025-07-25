- **Cell Format**: Use this option to choose how to format the data in cells. Refer to [Google Sheets API | CellFormat](https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets/cells#CellFormat) for more information.
    - **Let Google Sheets format** (default): n8n formats text and numbers in the cells according to Google Sheets' default settings. 
    - **Let n8n format**: New cells in your sheet will have the same data types as the input data provided by n8n.
- **Data Location on Sheet**: Use this option when you need to specify the data range on your sheet.
    - **Header Row**: Specify the row index that contains the column headers.
    - **First Data Row**: Specify the row index where the actual data starts.
- **Handling extra fields in input**: When using **Mapping Column Mode > Map Automatically**, use this option to decide how to handle fields in the input data that don't match any existing columns in the sheet.
    - **Insert in New Column(s)** (default): Adds new columns for any extra data.
    - **Ignore Them**: Ignores extra data that don't match the existing columns. 
    - **Error**: Throws an error and stops execution. 
- **Use Append**: Turn on this option to use the [Google API append endpoint](https://developers.google.com/sheets/api/guides/values#append_values) for adding new data rows.
    - By default, n8n appends empty rows or columns and then adds the new data. This approach can ensure data alignment but may be less efficient. Using the append endpoint can lead to better performance by minimizing the number of API calls and simplifying the process. But if the existing sheet data has inconsistencies such as gaps or breaks between rows and columns, n8n may add the new data in the wrong place, leading to misalignment issues.
    - Use this option when performance is a priority and the data structure in the sheet is consistent without gaps.

