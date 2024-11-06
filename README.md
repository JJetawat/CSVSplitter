# CSV Splitter for Mendix

This module enables efficient splitting of large CSV files into smaller, manageable chunks, stored as separate `FileDocument` objects in the Mendix environment. It’s ideal for applications requiring data processing, archiving, or migration workflows that involve extensive datasets. By processing files line-by-line, it minimizes memory usage while allowing users to customize chunk sizes.

---

## Typical Usage Scenario

The CSV Splitter is designed to help applications handle large CSV files more effectively by dividing them into smaller chunks. This is especially useful for applications that need to process or archive data in parts, improving both performance and manageability.

**Use Cases:**
- Batch data processing where smaller chunks are preferred
- Data archiving workflows in need of manageable file sizes
- Data migration projects requiring division of large CSV files

---

## Features and Limitations

### Features
- **Memory-Efficient**: Reads files line-by-line, avoiding memory overload from loading the entire file at once.
- **Customizable Chunk Size**: Allows specification of rows per file, making it adaptable for different data sizes and needs.
- **Integrated with Mendix Database**: Each chunk is stored as a separate Mendix `FileDocument`, making retrieval straightforward.

### Limitations
- **Header Handling**: The module includes the CSV header only in the **first** split file. If you need the header in all split files, you will need to add custom logic.
- **Knowledge Requirement**: Basic familiarity with the Mendix Core API may be helpful for advanced customization.

---

## Dependencies

- **Mendix Core API**: Ensure permissions are set for file creation and database operations, as this module uses Mendix Core functions for file handling.
- **Java Runtime**: Required for file operations, as the module relies on Java for CSV processing.

---

## Installation

1. **Download and Import**: Obtain the module from the Mendix Marketplace and import it into your Mendix project.
2. **Set Up Permissions**: Verify that your application has the necessary permissions to read, write, and store files in the Mendix database.
3. **Configure Java Actions**: Ensure that Java actions are enabled in your Mendix environment to support the file-splitting functionality.

---

## Configuration

1. **Set Row Limit per File**: Adjust the `rowsPerFile` parameter to specify how many rows should be included in each split file.
2. **Custom Header Logic (Optional)**: If you need the header to appear in all split files or have other header-related requirements, modify the main logic to handle the header accordingly.

---

## Known Issues

- **Header Duplication**: By default, the header is included only in the first split file. If you need to add the header to each split file, additional customization is required.
- **Large File Performance**: Very large files may still cause performance issues if the `rowsPerFile` setting is too high.

---

## Frequently Asked Questions

**Q: Can I specify custom file names for each chunk?**  
A: Yes, you can customize the `createFileDocument` method to define a custom naming convention for each chunk.

**Q: How do I ensure the header appears in each split file?**  
A: Modify the main split logic to include the header in each chunk if desired.

**Q: What if I encounter memory issues with extremely large files?**  
A: Lower the `rowsPerFile` count to create smaller chunks, which can help manage memory usage.

---

This module provides a robust solution for splitting large CSV files within Mendix, enhancing performance and data management capabilities.
