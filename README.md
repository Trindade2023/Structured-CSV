# Structured CSV (SCSV)

Structured CSV (SCSV) is an extension of the traditional CSV (Comma-Separated Values) format that adds a structured approach to data organization. While CSV represents data in a flat, tabular form with each line containing a record, SCSV introduces a header line that specifies column names and data types. This makes it easier to interpret and process the data, especially when dealing with complex datasets.

## Structure and Example

The SCSV format begins with a header line that starts with `#SCSV` to indicate the usage of SCSV. The subsequent line specifies the names and data types of each column, separated by commas. Here's an example of the SCSV structure:

    #SCSV v1.0
    Name:String,Age:Int,Email:String
    John,25,john@example.com
    Mary,30,mary@example.com

In the above example, we have three columns defined: "Name" of type "String," "Age" of type "Int" (integer), and "Email" of type "String." The first line after the header contains the actual data values for each column.

## Advantages of SCSV

- **Simplicity**: SCSV maintains the simplicity of the CSV format while adding structure to the data. It is easy to understand and work with, requiring minimal effort for implementation and integration.

- **Readability**: The inclusion of column names and data types in the header line enhances the readability of SCSV files. Developers and users can quickly grasp the structure of the data without relying on external documentation or assumptions.

- **Flexible Data Types**: SCSV supports various data types, such as strings, integers, floating-point numbers, dates, and more. This versatility allows for accurate representation and manipulation of different kinds of data in a standardized manner.

- **Efficient Bandwidth Utilization**: By organizing data in a structured format, SCSV reduces bandwidth consumption compared to other formats that require additional metadata or encoding. This efficiency is particularly valuable in scenarios where network resources are limited or expensive.

- **Improved Performance**: Due to its simplicity and optimized data organization, SCSV enables faster parsing and processing. Systems can handle large SCSV files more efficiently, leading to improved performance and reduced computational overhead.

- **Energy Efficiency**: The lightweight nature of SCSV contributes to lower energy consumption, making it suitable for resource-constrained environments, energy-efficient devices, and IoT applications. It helps minimize the energy footprint while maintaining effective data representation.

- **Version Control**: SCSV incorporates a version control system to ensure evolution with backward compatibility. The current version is indicated in the header line, allowing for future enhancements while maintaining compatibility with older implementations.

- **Escape Characters**: SCSV uses the escape character `"` to handle fields that contain commas. If a field needs to include a comma, it should be enclosed in double quotes (`"`). For example:
 
      #SCSV v1.0
      Name:String,Age:Int,Email:String
      John,25,john@example.com
      "Smith, Jr.",30,smith@example.com

The second record in the above example demonstrates the use of escape characters to include a comma within the "Name" field.

## Advanced Features

### Advanced Metadata

In addition to the existing functionality, SCSV now supports advanced metadata options inspired by SQL. Users can leverage these options to create more sophisticated files with features like indexing and primary keys. For a simple file, users can continue to follow the previous structure, but for advanced features, additional metadata can be included. Here's an example:

      #SCSV v1.0
      Name:String(100),Age:Int,Email:String(255)
      John,25,john@example.com
      Mary,30,mary@example.com

In this example, the "Name" column has a maximum length of 100 characters, and the "Email" column has a maximum length of 255 characters.

### SQL Native Data Types

SCSV supports SQL native data types, expanding its versatility. Users can utilize data types like "Text," "Numeric," "Date," and others, similar to those found in SQL databases. Here's an example:

    #SCSV v1.0
    Name:Text,Age:Int,Email:Text
    John,25,john@example.com
    Mary,30,mary@example.com

In this example, the "Name" and "Email" columns are defined as "Text" data types.

### Example with Primary Keys and Indexing

    #SCSV v1.0
    ID:Int PRIMARY KEY, Name:String(100), Age:Int INDEX, Email:String(255)
    1, John, 25, john@example.com
    2, Mary, 30, mary@example.com
    3, Jane, 35, jane@example.com

In this example, we have added metadata to the columns. The "ID" column is specified as the primary key, ensuring each record has a unique identifier. The "Age" column is indexed for faster retrieval of records based on age. This indexing feature enhances the performance of queries that involve filtering or sorting by age.

## License and Community Collaboration

SCSV is released under the MIT License, granting developers the freedom to use, modify, and distribute the format without significant restrictions. The intention is to foster a collaborative community around SCSV, where developers can contribute to the creation of libraries, perform extensive testing on different platforms, and share their experiences and insights.

We invite developers to join the SCSV community, participate in discussions, and contribute to its growth and development. By working together, we can expand the range of tools and utilities available, ensure compatibility across platforms, and promote the adoption of SCSV as a structured data interchange format.
